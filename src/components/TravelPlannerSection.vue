<template>
  <section id="travel-planner" class="travel-planner-section">
    <div class="container">
      <h2 class="section-title">Jouw Afrika-avontuur begint hier!</h2>
      <p class="section-intro">
        Ga je mee off the beaten track? Ontvang binnen no-time een indicatie en ga meteen los met plannen! 
        We stemmen de volledige reis op jouw wensen af.
      </p>

        <div class="planner-container" @click="handlePlannerClick">
          <div class="scroll-lock-indicator" v-if="isScrollLocked">
            <i class="fas fa-lock"></i>
            <span>Scrolling vergrendeld - Druk ESC of klik buiten om te ontgrendelen</span>
          </div>
          <div class="scroll-hint" v-if="plannerFullyVisible && !isScrollLocked">
            <i class="fas fa-mouse-pointer"></i>
            <span>Klik hier om scrolling te vergrendelen tijdens het invullen</span>
          </div>
          <div class="planner-steps">
          <div class="step" :class="{ active: currentStep >= 1, completed: currentStep > 1 }">
            <div class="step-number">1</div>
            <div class="step-title">Destinations</div>
          </div>
          <div class="step" :class="{ active: currentStep >= 2, completed: currentStep > 2 }">
            <div class="step-number">2</div>
            <div class="step-title">Preferences</div>
          </div>
          <div class="step" :class="{ active: currentStep >= 3, completed: currentStep > 3 }">
            <div class="step-number">3</div>
            <div class="step-title">Details</div>
          </div>
          <div class="step" :class="{ active: currentStep >= 4 }">
            <div class="step-number">4</div>
            <div class="step-title">Your Plan</div>
          </div>
        </div>

        <div class="planner-content">
          <!-- Step 1: Destination Selection -->
          <div v-if="currentStep === 1" class="planner-step fade-in">
            <h3>Welk land wil jij ontdekken?</h3>
            <div class="destination-selector">
              <div 
                v-for="destination in destinations" 
                :key="destination.id"
                class="destination-option"
                :class="{ selected: travelPlan.destinations.includes(destination.id) }"
                @click="toggleDestination(destination.id)"
              >
                <div class="destination-image" :style="`background-image: url('${destination.image}')`"></div>
                <div class="destination-info">
                  <h4>{{ destination.name }}</h4>
                  <p>{{ destination.description }}</p>
                  <div class="destination-tags">
                    <span v-for="tag in destination.tags" :key="tag" class="tag">{{ tag }}</span>
                  </div>
                </div>
              </div>
            </div>
            <button 
              @click="nextStep" 
              :disabled="travelPlan.destinations.length === 0"
              class="continue-btn"
            >
              Continue <i class="fas fa-arrow-right"></i>
            </button>
          </div>

          <!-- Step 2: Travel Preferences -->
          <div v-if="currentStep === 2" class="planner-step fade-in">
            <h3>Met wie ga jij op pad?</h3>
            <div class="preferences-grid">
              <div class="preference-group">
                <label>Type reiziger</label>
                <div class="duration-options">
                  <div 
                    v-for="duration in durationOptions" 
                    :key="duration.value"
                    class="option-card"
                    :class="{ selected: travelPlan.duration === duration.value }"
                    @click="travelPlan.duration = duration.value"
                  >
                    <i :class="duration.icon"></i>
                    <span>{{ duration.label }}</span>
                  </div>
                </div>
              </div>

              <div class="preference-group">
                <label>Uit wat voor type personen bestaat jouw groep?</label>
                <div class="group-composition-grid">
                  <div 
                    v-for="groupType in groupComposition" 
                    :key="groupType.id"
                    class="composition-card"
                    :class="{ selected: travelPlan.groupComposition.includes(groupType.id) }"
                    @click="toggleGroupComposition(groupType.id)"
                  >
                    <i :class="groupType.icon"></i>
                    <span>{{ groupType.name }}</span>
                  </div>
                </div>
              </div>

              <div class="preference-group">
                <label>Hoe snel wil jij reizen?</label>
                <div class="travel-pace-options">
                  <div 
                    v-for="pace in travelPace" 
                    :key="pace.value"
                    class="pace-card"
                    :class="{ selected: travelPlan.travelPace === pace.value }"
                    @click="travelPlan.travelPace = pace.value"
                  >
                    <i :class="pace.icon"></i>
                    <div class="pace-info">
                      <span class="pace-name">{{ pace.name }}</span>
                      <span class="pace-desc">{{ pace.description }}</span>
                    </div>
                  </div>
                </div>
              </div>

              <div class="preference-group">
                <label>Wil je een touristisch gebied of juist niet?</label>
                <div class="tourism-preference">
                  <div 
                    v-for="tourism in tourismTypes" 
                    :key="tourism.value"
                    class="tourism-card"
                    :class="{ selected: travelPlan.tourismPreference === tourism.value }"
                    @click="travelPlan.tourismPreference = tourism.value"
                  >
                    <i :class="tourism.icon"></i>
                    <div class="tourism-info">
                      <span class="tourism-name">{{ tourism.name }}</span>
                      <span class="tourism-desc">{{ tourism.description }}</span>
                    </div>
                  </div>
                </div>
              </div>

              <div class="preference-group">
                  <label>Prijsindicatie</label>
                <div class="budget-slider-container">
                  <input 
                    type="range" 
                    min="0" 
                    max="4" 
                    v-model="travelPlan.budgetIndex"
                    class="budget-slider"
                  >
                  <div class="budget-labels">
                    <span v-for="(budget, index) in budgetOptions" :key="index" 
                          :class="{ active: travelPlan.budgetIndex == index }">
                      {{ budget.label }}
                    </span>
                  </div>
                  <div class="budget-description">
                    {{ budgetOptions[travelPlan.budgetIndex].description }}
                  </div>
                </div>
              </div>

              <div class="preference-group">
                  <label>Waar heb je zin in?</label>
                <div class="activities-grid">
                  <div 
                    v-for="activity in activities" 
                    :key="activity.id"
                    class="activity-card"
                    :class="{ selected: travelPlan.activities.includes(activity.id) }"
                    @click="toggleActivity(activity.id)"
                  >
                    <i :class="activity.icon"></i>
                    <span>{{ activity.name }}</span>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="step-navigation">
              <button @click="prevStep" class="back-btn">
                <i class="fas fa-arrow-left"></i> Back
              </button>
              <button @click="nextStep" class="continue-btn">
                Continue <i class="fas fa-arrow-right"></i>
              </button>
            </div>
          </div>

          <!-- Step 3: Personal Details -->
          <div v-if="currentStep === 3" class="planner-step fade-in">
            <h3>Vertel ons over jouw droomreis</h3>
            <div class="details-form">
              <div class="form-row">
                <div class="form-group">
                  <label>Your Name</label>
                  <input type="text" v-model="travelPlan.name" placeholder="Enter your name">
                </div>
                <div class="form-group">
                  <label>Email</label>
                  <input type="email" v-model="travelPlan.email" placeholder="your@email.com">
                </div>
              </div>
              
              <div class="form-row">
                <div class="form-group">
                  <label>Preferred Travel Dates</label>
                  <input type="text" v-model="travelPlan.dates" placeholder="e.g., March 2024">
                </div>
                <div class="form-group">
                  <label>Number of Travelers</label>
                  <select v-model="travelPlan.travelers">
                    <option value="">Select...</option>
                    <option value="1">Just me</option>
                    <option value="2">2 travelers</option>
                    <option value="3-4">3-4 travelers</option>
                    <option value="5+">5+ travelers</option>
                  </select>
                </div>
              </div>

              <div class="form-row">
                <div class="form-group">
                  <label>Welk type accommodatie spreekt je aan?</label>
                  <select v-model="travelPlan.accommodationType">
                    <option value="">Kies een optie...</option>
                    <option v-for="acc in accommodationTypes" :key="acc.id" :value="acc.id">
                      {{ acc.name }}
                    </option>
                  </select>
                </div>
                <div class="form-group">
                  <label>Wat is jouw fysieke niveau?</label>
                  <select v-model="travelPlan.physicalLevel">
                    <option value="">Kies een niveau...</option>
                    <option v-for="level in physicalLevels" :key="level.id" :value="level.id">
                      {{ level.name }} - {{ level.description }}
                    </option>
                  </select>
                </div>
              </div>

              <div class="form-group">
                <label>Eetvoorkeuren</label>
                <div class="food-preferences">
                  <div 
                    v-for="food in foodPreferences" 
                    :key="food.id"
                    class="food-card"
                    :class="{ selected: travelPlan.foodPreference === food.id }"
                    @click="travelPlan.foodPreference = food.id"
                  >
                    <i :class="food.icon"></i>
                    <span>{{ food.name }}</span>
                  </div>
                </div>
              </div>

              <div class="form-group">
                <label>Speciale wensen of interesses</label>
                <textarea v-model="travelPlan.notes" placeholder="Vertel ons over specifieke interesses, medische behoeften, of unieke ervaringen die je zoekt..."></textarea>
              </div>
            </div>

            <div class="step-navigation">
              <button @click="prevStep" class="back-btn">
                <i class="fas fa-arrow-left"></i> Back
              </button>
              <button @click="generatePlan" class="continue-btn">
                Generate My Plan <i class="fas fa-magic"></i>
              </button>
            </div>
          </div>

          <!-- Step 4: Generated Plan -->
          <div v-if="currentStep === 4" class="planner-step fade-in">
            <h3>Your Personalized African Adventure</h3>
            <div class="generated-plan">
              <div class="plan-header">
                <h4>{{ travelPlan.name }}'s African Journey</h4>
                <div class="plan-summary">
                  <span class="duration">{{ getDurationLabel() }}</span>
                  <span class="budget">{{ getBudgetLabel() }}</span>
                  <span class="travelers">{{ travelPlan.travelers }} {{ travelPlan.travelers === '1' ? 'traveler' : 'travelers' }}</span>
                </div>
              </div>

              <div class="plan-destinations">
                <h5>Your Destinations</h5>
                <div class="plan-destination-list">
                  <div v-for="destId in travelPlan.destinations" :key="destId" class="plan-destination">
                    <div class="dest-image" :style="`background-image: url('${getDestination(destId).image}')`"></div>
                    <div class="dest-info">
                      <h6>{{ getDestination(destId).name }}</h6>
                      <p>{{ getDestination(destId).planDescription }}</p>
                    </div>
                  </div>
                </div>
              </div>

              <div class="plan-activities">
                <h5>Included Activities</h5>
                <div class="activity-list">
                  <div v-for="activityId in travelPlan.activities" :key="activityId" class="plan-activity">
                    <i :class="getActivity(activityId).icon"></i>
                    <span>{{ getActivity(activityId).name }}</span>
                  </div>
                </div>
              </div>

              <div class="plan-cta">
                <button @click="downloadPlan" class="download-btn">
                  <i class="fas fa-download"></i> Download Itinerary
                </button>
                <button @click="contactExpert" class="contact-btn">
                  <i class="fas fa-phone"></i> Speak with Expert
                </button>
                <button @click="restartPlanner" class="restart-btn">
                  <i class="fas fa-refresh"></i> Start Over
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TravelPlannerSection',
  data() {
    return {
      currentStep: 1,
      isScrollLocked: false,
      plannerFullyVisible: false,
      scrollPosition: 0,
      travelPlan: {
        destinations: [],
        duration: '',
        budgetIndex: 2,
        activities: [],
        groupComposition: [],
        travelPace: '',
        tourismPreference: '',
        accommodationType: '',
        foodPreference: '',
        physicalLevel: '',
        name: '',
        email: '',
        dates: '',
        travelers: '',
        notes: ''
      },
      destinations: [
        {
          id: 'kruger',
          name: 'Kruger National Park',
          image: './images/kruger-national-park3.jpeg',
          description: 'Iconic Big Five safari experiences in South Africa\'s premier game reserve',
          tags: ['Big Five', 'Safari', 'Wildlife Photography'],
          planDescription: '3-4 days of game drives, luxury lodge accommodation, and guided bush walks'
        },
        {
          id: 'hluhluwe',
          name: 'Hluhluwe-iMfolozi',
          image: './images/aa-Hluhluwe-lion.jpeg',
          description: 'Africa\'s oldest game reserve, famous for rhino conservation',
          tags: ['Rhino Sanctuary', 'Conservation', 'Walking Safaris'],
          planDescription: '2-3 days focused on rhino tracking and conservation education'
        },
        {
          id: 'chobe',
          name: 'Chobe National Park',
          image: './images/Landenpagina-Botswana-leeuw-Chobe-Emiel-Kusters-800x500-1.jpg',
          description: 'Botswana\'s elephant paradise with river safaris',
          tags: ['Elephants', 'River Safari', 'Botswana'],
          planDescription: 'River cruises, elephant encounters, and luxury tented camp experience'
        },
        {
          id: 'sodwana',
          name: 'Sodwana Bay',
          image: './images/diving-south-africa-sodwana-bay-anna-reef.jpg',
          description: 'World-class diving with pristine coral reefs',
          tags: ['Diving', 'Marine Life', 'Coral Reefs'],
          planDescription: 'Scuba diving, snorkeling, and marine conservation experiences'
        },
        {
          id: 'klaserie',
          name: 'Klaserie Private Reserve',
          image: './images/klaserie-private-game-reserve.jpg',
          description: 'Exclusive luxury safari experience in private concession',
          tags: ['Luxury', 'Private Reserve', 'Exclusive'],
          planDescription: 'Private game drives, luxury lodge, and personalized safari experience'
        },
        {
          id: 'blyde',
          name: 'Blyde River Canyon',
          image: './images/Kopie-van-Blyde-River-Canyon.jpg',
          description: 'Spectacular canyon views and dramatic landscapes',
          tags: ['Scenic Views', 'Hiking', 'Photography'],
          planDescription: 'Scenic drives, hiking trails, and photography workshops'
        }
      ],
      durationOptions: [
        { value: 'familiereis', label: 'Familiereis', icon: 'fas fa-users' },
        { value: 'lovebirds', label: 'Lovebirds', icon: 'fas fa-heart' },
        { value: 'vriendenreis', label: 'Vriendenreis', icon: 'fas fa-user-friends' },
        { value: 'lustrumreis', label: 'Lustrumreis', icon: 'fas fa-graduation-cap' }
      ],
      budgetOptions: [
        { label: 'Budget', description: '€2.000 - €3.000 per persoon', range: '€2k-3k' },
        { label: 'Comfort', description: '€3.000 - €5.000 per persoon', range: '€3k-5k' },
        { label: 'Premium', description: '€5.000 - €8.000 per persoon', range: '€5k-8k' },
        { label: 'Luxe', description: '€8.000 - €12.000 per persoon', range: '€8k-12k' },
        { label: 'Ultra-luxe', description: '€12.000+ per persoon', range: '€12k+' }
      ],
      activities: [
        { id: 'safari', name: 'Safari & Wildlife', icon: 'fas fa-binoculars' },
        { id: 'hiking', name: 'Wandelen & Trekking', icon: 'fas fa-hiking' },
        { id: 'cultural', name: 'Lokale ervaringen', icon: 'fas fa-users' },
        { id: 'photography', name: 'Fotografie', icon: 'fas fa-camera' },
        { id: 'beach', name: 'Strand & Ontspanning', icon: 'fas fa-umbrella-beach' },
        { id: 'adventure', name: 'Avontuur & Sport', icon: 'fas fa-mountain' },
        { id: 'conservation', name: 'Natuurbehoud', icon: 'fas fa-leaf' },
        { id: 'luxury', name: 'Luxe accommodaties', icon: 'fas fa-gem' }
      ],
      groupComposition: [
        { id: 'young-adults', name: 'Jongvolwassenen', icon: 'fas fa-users' },
        { id: 'families-kids', name: 'Gezinnen met kinderen', icon: 'fas fa-child' },
        { id: 'couples', name: 'Stellen', icon: 'fas fa-heart' },
        { id: 'seniors', name: '50+ reizigers', icon: 'fas fa-user-check' },
        { id: 'adventure-seekers', name: 'Avonturiers', icon: 'fas fa-mountain' },
        { id: 'culture-lovers', name: 'Cultuurliefhebbers', icon: 'fas fa-museum' }
      ],
      travelPace: [
        { 
          value: 'slow', 
          name: 'Rustig aan', 
          description: 'Tijd nemen voor elke bestemming', 
          icon: 'fas fa-leaf' 
        },
        { 
          value: 'moderate', 
          name: 'Gemiddeld tempo', 
          description: 'Balans tussen ontspanning en ontdekking', 
          icon: 'fas fa-walking' 
        },
        { 
          value: 'active', 
          name: 'Actief tempo', 
          description: 'Veel zien en doen in korte tijd', 
          icon: 'fas fa-running' 
        }
      ],
      tourismTypes: [
        { 
          value: 'off-beaten', 
          name: 'Off the beaten track', 
          description: 'Onontdekte plekken, weg van toeristen', 
          icon: 'fas fa-compass' 
        },
        { 
          value: 'mixed', 
          name: 'Combinatie', 
          description: 'Mix van bekende en verborgen parels', 
          icon: 'fas fa-balance-scale' 
        },
        { 
          value: 'popular', 
          name: 'Populaire bestemmingen', 
          description: 'Bekende highlights en must-sees', 
          icon: 'fas fa-star' 
        }
      ],
      accommodationTypes: [
        { id: 'camping', name: 'Kamperen & glamping', icon: 'fas fa-campground' },
        { id: 'guesthouse', name: 'Lokale guesthouses', icon: 'fas fa-home' },
        { id: 'mid-range', name: 'Comfort hotels', icon: 'fas fa-bed' },
        { id: 'luxury', name: 'Luxury lodges', icon: 'fas fa-crown' }
      ],
      foodPreferences: [
        { id: 'local', name: 'Lokale keuken', icon: 'fas fa-utensils' },
        { id: 'international', name: 'Internationale keuken', icon: 'fas fa-globe' },
        { id: 'vegetarian', name: 'Vegetarisch/Vegan', icon: 'fas fa-seedling' },
        { id: 'dietary', name: 'Speciale dieetwensen', icon: 'fas fa-apple-alt' }
      ],
      physicalLevels: [
        { id: 'low', name: 'Ontspannen', description: 'Minimale fysieke inspanning', icon: 'fas fa-couch' },
        { id: 'moderate', name: 'Gemiddeld', description: 'Wat wandelen en lichte activiteiten', icon: 'fas fa-walking' },
        { id: 'active', name: 'Actief', description: 'Veel wandelen en sport activiteiten', icon: 'fas fa-hiking' },
        { id: 'extreme', name: 'Uitdagend', description: 'Intensieve fysieke activiteiten', icon: 'fas fa-mountain' }
      ]
    }
  },
  mounted() {
    this.initializeScrollLock();
  },
  beforeUnmount() {
    this.disableScrollLock();
  },
  watch: {
    currentStep() {
      this.$nextTick(() => {
        const currentStepEl = document.querySelector('.planner-step');
        if (currentStepEl) {
          currentStepEl.classList.add('fade-in');
        }
      });
    }
  },
  methods: {
    nextStep() {
      if (this.currentStep < 4) {
        this.currentStep++;
      }
    },
    prevStep() {
      if (this.currentStep > 1) {
        this.currentStep--;
      }
    },
    generatePlan() {
      this.currentStep = 4;
    },
    restartPlanner() {
      this.currentStep = 1;
      this.travelPlan = {
        destinations: [],
        duration: '',
        budgetIndex: 2,
        activities: [],
        groupComposition: [],
        travelPace: '',
        tourismPreference: '',
        accommodationType: '',
        foodPreference: '',
        physicalLevel: '',
        name: '',
        email: '',
        dates: '',
        travelers: '',
        notes: ''
      };
    },
    toggleDestination(destinationId) {
      const index = this.travelPlan.destinations.indexOf(destinationId);
      if (index > -1) {
        this.travelPlan.destinations.splice(index, 1);
      } else {
        this.travelPlan.destinations.push(destinationId);
      }
    },
    toggleActivity(activityId) {
      const index = this.travelPlan.activities.indexOf(activityId);
      if (index > -1) {
        this.travelPlan.activities.splice(index, 1);
      } else {
        this.travelPlan.activities.push(activityId);
      }
    },
    toggleGroupComposition(groupId) {
      const index = this.travelPlan.groupComposition.indexOf(groupId);
      if (index > -1) {
        this.travelPlan.groupComposition.splice(index, 1);
      } else {
        this.travelPlan.groupComposition.push(groupId);
      }
    },
    getDestination(id) {
      return this.destinations.find(dest => dest.id === id);
    },
    getActivity(id) {
      return this.activities.find(activity => activity.id === id);
    },
    getDurationLabel() {
      const duration = this.durationOptions.find(d => d.value === this.travelPlan.duration);
      return duration ? duration.label : 'Custom Duration';
    },
    getBudgetLabel() {
      return this.budgetOptions[this.travelPlan.budgetIndex].range;
    },
    downloadPlan() {
      alert('Your personalized African adventure itinerary will be sent to your email!');
    },
    contactExpert() {
      alert('Our travel expert will contact you within 24 hours to discuss your African adventure!');
    },
    initializeScrollLock() {
      // Create intersection observer to detect when travel planner is FULLY in view
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          const plannerContainer = entry.target.querySelector('.planner-container');
          if (entry.isIntersecting && plannerContainer) {
            // Check if the planner container is fully visible
            const containerRect = plannerContainer.getBoundingClientRect();
            const windowHeight = window.innerHeight;
            
            // Only lock if the entire container fits in the viewport with some margin
            const isFullyVisible = containerRect.top >= 50 && containerRect.bottom <= windowHeight - 50;
            
            if (isFullyVisible) {
              // Only auto-lock when clicking in the planner, not just when scrolling to it
              this.plannerFullyVisible = true;
            } else {
              this.plannerFullyVisible = false;
              this.disableScrollLock();
            }
          } else {
            // User has scrolled away from travel planner - always unlock
            this.plannerFullyVisible = false;
            this.disableScrollLock();
          }
        });
      }, { 
        threshold: 0.95, // Trigger when 95% of the section is visible
        rootMargin: '-50px 0px -50px 0px' // Require some margin from viewport edges
      });

      // Observe the travel planner section
      const plannerSection = document.getElementById('travel-planner');
      if (plannerSection) {
        observer.observe(plannerSection);
      }

      // Listen for clicks within the planner to enable scroll lock (only when fully visible)
      const plannerContainer = document.querySelector('.planner-container');
      if (plannerContainer) {
        plannerContainer.addEventListener('click', (e) => {
          if (this.plannerFullyVisible) {
            this.enableScrollLock();
          }
        });
      }

      // Listen for clicks outside the planner to disable scroll lock
      document.addEventListener('click', (e) => {
        const plannerSection = document.getElementById('travel-planner');
        if (plannerSection && !plannerSection.contains(e.target)) {
          this.disableScrollLock();
        }
      });

      // Listen for escape key to disable scroll lock
      document.addEventListener('keydown', (e) => {
        if (e.key === 'Escape') {
          this.disableScrollLock();
        }
      });

      // Listen for scroll events to allow scrolling past the planner
      let scrollTimeout;
      window.addEventListener('scroll', () => {
        if (this.isScrollLocked) {
          // Clear timeout to debounce scroll events
          clearTimeout(scrollTimeout);
          
          // Set a timeout to check if user is trying to scroll past
          scrollTimeout = setTimeout(() => {
            const plannerSection = document.getElementById('travel-planner');
            if (plannerSection) {
              const rect = plannerSection.getBoundingClientRect();
              const windowHeight = window.innerHeight;
              
              // If planner is no longer in view or user scrolled significantly past it, unlock
              if (rect.bottom < 0 || rect.top > windowHeight) {
                this.disableScrollLock();
              }
            }
          }, 100);
        }
      });
    },
    enableScrollLock() {
      if (!this.isScrollLocked) {
        // Store current scroll position
        this.scrollPosition = window.pageYOffset;
        
        // Prevent body scrolling
        document.body.style.overflow = 'hidden';
        document.documentElement.style.overflow = 'hidden';
        document.body.style.position = 'fixed';
        document.body.style.top = `-${this.scrollPosition}px`;
        document.body.style.width = '100%';
        
        // Add a class to indicate scroll is locked
        document.body.classList.add('scroll-locked');
        
        // Update component state
        this.isScrollLocked = true;
        
        // Ensure the planner content is scrollable
        const plannerContent = document.querySelector('.planner-content');
        if (plannerContent) {
          plannerContent.style.overflowY = 'auto';
        }
      }
    },
    disableScrollLock() {
      if (this.isScrollLocked) {
        // Re-enable body scrolling
        document.body.style.overflow = '';
        document.documentElement.style.overflow = '';
        document.body.style.position = '';
        document.body.style.top = '';
        document.body.style.width = '';
        
        // Restore scroll position
        window.scrollTo(0, this.scrollPosition || 0);
        
        // Remove the scroll lock class
        document.body.classList.remove('scroll-locked');
        
        // Update component state
        this.isScrollLocked = false;
      }
    },
    handlePlannerClick() {
      if (this.plannerFullyVisible) {
        this.enableScrollLock();
      }
    }
  }
}
</script>
