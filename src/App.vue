<template>
  <div class="app">
    <!-- Navigation -->
    <nav class="navigation">
      <div class="nav-container">
        <div class="logo">Made with True Love</div>
        <div class="nav-links">
          <a href="#destinations">Destinations</a>
          <a href="#wildlife">Experiences</a>
          <a href="#travel-planner">Travel Planner</a>
          <a href="#impact">Impact</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero-section">
      <div class="hero-overlay"></div>
      <div class="hero-content">
        <h1 class="hero-title">
          AFRICAN<br>
          <span class="title-highlight">ADVENTURES</span>
        </h1>
        <div class="hero-subtitle">A Journey of Discovery</div>
        <div class="hero-years">2010-2025</div>
        <p class="hero-description">
          Welcome to a celebration of Africa's most transformative destinations and experiences. 
          These places represent more than just travel; they signify a remarkable journey of discovery 
          and connection under the vast African sky. This collection showcases legendary landscapes 
          and the establishment of unforgettable memories that captivate travelers worldwide.
        </p>
        <div class="hero-inspiration">
          <h3>An adventure that inspires</h3>
          <p>
            These African destinations offer more than unprecedented beauty; they are a testament to the power 
            of nature and wildlife. From the iconic Big Five to breathtaking landscapes, each location provides 
            experiences that redefine what is possible in travel, inspiring wanderers and adventurers across the world.
          </p>
        </div>
      </div>
    </section>

    <!-- Quick Links -->
    <section class="quick-links">
      <div class="container">
        <h2>QuickLinks</h2>
        <div class="links-grid">
          <a href="#destinations" class="quick-link">Destinations</a>
          <a href="#wildlife" class="quick-link">Wildlife Experiences</a>
          <a href="#cultural" class="quick-link">Cultural Adventures</a>
          <a href="#luxury" class="quick-link">Luxury Safaris</a>
          <a href="#impact" class="quick-link">Our Impact</a>
        </div>
      </div>
    </section>

    <!-- Key Destinations -->
    <section id="destinations" class="destinations-section">
      <div class="container">
        <h2 class="section-title">Key Destinations</h2>
        <p class="section-intro">
          In any remarkable story of adventure, there are places whose beauty becomes the cornerstone of unforgettable experiences. 
          Our African destinations are graced by such locations - stunning, diverse, and driven by an unwavering passion for conservation. 
          This section celebrates the key destinations that play pivotal roles in shaping one of the most exhilarating travel experiences on Earth.
        </p>

        <div class="destinations-grid">
          <div class="destination-card">
            <div class="destination-image" style="background-image: url('./images/kruger-national-park3.jpeg')"></div>
            <div class="destination-content">
              <h3>Kruger National Park</h3>
              <div class="destination-type">South Africa</div>
              <p class="destination-description">
                Home to the legendary Big Five and countless other species. Kruger represents the pinnacle of African safari experiences.
              </p>
              <div class="destination-highlight">
                <strong>Highlight:</strong> Over 500 bird species and the highest density of wildlife in Africa.
              </div>
            </div>
          </div>

          <div class="destination-card">
            <div class="destination-image" style="background-image: url('./images/aa-Hluhluwe-lion.jpeg')"></div>
            <div class="destination-content">
              <h3>Hluhluwe-iMfolozi</h3>
              <div class="destination-type">Game Reserve</div>
              <p class="destination-description">
                Africa's oldest proclaimed nature reserve, known for its successful rhino conservation program and diverse wildlife.
              </p>
              <div class="destination-highlight">
                <strong>Conservation:</strong> Saved the white rhinoceros from extinction through dedicated conservation efforts.
              </div>
            </div>
          </div>

          <div class="destination-card">
            <div class="destination-image" style="background-image: url('./images/klaserie-private-game-reserve.jpg')"></div>
            <div class="destination-content">
              <h3>Klaserie Private Reserve</h3>
              <div class="destination-type">Luxury Safari</div>
              <p class="destination-description">
                An exclusive wilderness area offering intimate wildlife encounters and luxury accommodation in pristine African bush.
              </p>
              <div class="destination-highlight">
                <strong>Experience:</strong> Private game drives and walking safaris with expert guides.
              </div>
            </div>
          </div>

          <div class="destination-card">
            <div class="destination-image" style="background-image: url('./images/Landenpagina-Botswana-leeuw-Chobe-Emiel-Kusters-800x500-1.jpg')"></div>
            <div class="destination-content">
              <h3>Chobe National Park</h3>
              <div class="destination-type">Botswana</div>
              <p class="destination-description">
                Famous for having the largest concentration of elephants in Africa and spectacular river safaris along the Chobe River.
              </p>
              <div class="destination-highlight">
                <strong>Wildlife:</strong> Home to over 120,000 elephants and incredible bird diversity.
              </div>
            </div>
          </div>

          <div class="destination-card">
            <div class="destination-image" style="background-image: url('./images/diving-south-africa-sodwana-bay-anna-reef.jpg')"></div>
            <div class="destination-content">
              <h3>Sodwana Bay</h3>
              <div class="destination-type">Marine Adventure</div>
              <p class="destination-description">
                World-class diving destination with pristine coral reefs, whale sharks, and some of the most biodiverse marine life in Africa.
              </p>
              <div class="destination-highlight">
                <strong>Marine Life:</strong> Over 2000 fish species and spectacular coral formations.
              </div>
            </div>
          </div>

          <div class="destination-card">
            <div class="destination-image" style="background-image: url('./images/Kopie-van-Blyde-River-Canyon.jpg')"></div>
            <div class="destination-content">
              <h3>Blyde River Canyon</h3>
              <div class="destination-type">Natural Wonder</div>
              <p class="destination-description">
                One of the world's largest canyons, offering breathtaking views, dramatic landscapes, and unique geological formations.
              </p>
              <div class="destination-highlight">
                <strong>Views:</strong> The famous Three Rondavels and God's Window viewpoints.
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Wildlife Experiences -->
    <section id="wildlife" class="experiences-section">
      <div class="container">
        <h2 class="section-title">Unforgettable Wildlife Experiences</h2>
        
        <div class="experience-timeline">
          <div class="experience-item">
            <div class="experience-image" style="background-image: url('./images/AA-Ezulwini-Valley.jpeg')"></div>
            <div class="experience-content">
              <h3>The Great Migration</h3>
              <div class="experience-type">Seasonal Spectacle</div>
              <p>
                Witness one of nature's most incredible phenomena as millions of wildebeest, zebras, and gazelles 
                traverse the African plains in search of fresh grasslands.
              </p>
              <div class="experience-stats">
                <div class="stat">
                  <span class="stat-number">2M+</span>
                  <span class="stat-label">Animals</span>
                </div>
                <div class="stat">
                  <span class="stat-number">3,000km</span>
                  <span class="stat-label">Journey</span>
                </div>
              </div>
            </div>
          </div>

          <div class="experience-item reverse">
            <div class="experience-image" style="background-image: url('./images/Ezulwini-Valley2.jpeg')"></div>
            <div class="experience-content">
              <h3>Big Five Safari</h3>
              <div class="experience-type">Classic Adventure</div>
              <p>
                Encounter Africa's most iconic animals - lion, leopard, elephant, buffalo, and rhinoceros - 
                in their natural habitat across various game reserves and national parks.
              </p>
              <div class="experience-stats">
                <div class="stat">
                  <span class="stat-number">5</span>
                  <span class="stat-label">Iconic Species</span>
                </div>
                <div class="stat">
                  <span class="stat-number">20+</span>
                  <span class="stat-label">Parks Available</span>
                </div>
              </div>
            </div>
          </div>

          <div class="experience-item">
            <div class="experience-image" style="background-image: url('./images/Kosi-Bay1.jpeg')"></div>
            <div class="experience-content">
              <h3>Marine Adventures</h3>
              <div class="experience-type">Ocean Discovery</div>
              <p>
                Explore pristine marine ecosystems, from coral reef diving to whale watching, 
                and discover the incredible biodiversity beneath African waters.
              </p>
              <div class="experience-stats">
                <div class="stat">
                  <span class="stat-number">2,000+</span>
                  <span class="stat-label">Fish Species</span>
                </div>
                <div class="stat">
                  <span class="stat-number">Year-round</span>
                  <span class="stat-label">Whale Watching</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Impact Section -->
    <section id="impact" class="impact-section">
      <div class="container">
        <h2 class="section-title">Impact on Conservation</h2>
        <p class="section-intro">
          Our African adventures represent more than just incredible experiences; they contribute to vital conservation efforts 
          and sustainable tourism practices that protect these magnificent ecosystems for future generations.
        </p>

        <div class="impact-stats">
          <div class="impact-stat">
            <div class="stat-number">250%</div>
            <div class="stat-label">Conservation Funding Increase</div>
          </div>
          <div class="impact-stat">
            <div class="stat-number">180%</div>
            <div class="stat-label">Local Community Employment</div>
          </div>
          <div class="impact-stat">
            <div class="stat-number">95%</div>
            <div class="stat-label">Wildlife Population Recovery</div>
          </div>
          <div class="impact-stat">
            <div class="stat-number">50+</div>
            <div class="stat-label">Protected Areas Supported</div>
          </div>
        </div>

        <div class="impact-description">
          <p>
            As we reflect on these remarkable destinations, it is evident that their impact extends far beyond tourism. 
            These places have contributed to wildlife conservation, community development, and environmental protection, 
            leaving an indelible mark on both visitors and local ecosystems.
          </p>
        </div>
      </div>
    </section>

    <!-- Travel Plan Generator -->
    <section id="travel-planner" class="travel-planner-section">
      <div class="container">
        <h2 class="section-title">Create Your African Adventure</h2>
        <p class="section-intro">
          Tell us about your dream African journey and we'll create a personalized itinerary just for you.
        </p>

        <div class="planner-container">
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
              <h3>Choose Your Destinations</h3>
              <div class="destination-selector">
                <div 
                  v-for="destination in plannerDestinations" 
                  :key="destination.id"
                  class="destination-option"
                  :class="{ selected: travelPlan.destinations.includes(destination.id) }"
                  @click="togglePlannerDestination(destination.id)"
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
              <h3>Your Travel Style</h3>
              <div class="preferences-grid">
                <div class="preference-group">
                  <label>Travel Duration</label>
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
                  <label>Budget Range</label>
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
                  <label>Activities</label>
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
              <h3>Tell Us About You</h3>
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

                <div class="form-group">
                  <label>Special Requests or Interests</label>
                  <textarea v-model="travelPlan.notes" placeholder="Tell us about any special interests, dietary requirements, or specific experiences you're looking for..."></textarea>
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
                      <div class="dest-image" :style="`background-image: url('${getPlannerDestination(destId).image}')`"></div>
                      <div class="dest-info">
                        <h6>{{ getPlannerDestination(destId).name }}</h6>
                        <p>{{ getPlannerDestination(destId).planDescription }}</p>
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

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-left">
            <div class="footer-sections">
              <span>Sections</span>
              <div class="footer-links">
                <a href="#destinations">Destinations</a>
                <a href="#wildlife">Wildlife</a>
                <a href="#travel-planner">Travel Planner</a>
                <a href="#impact">Impact</a>
              </div>
            </div>
          </div>
          <div class="footer-right">
            <div class="footer-credits">
              <p>Made with <strong>True Love</strong> by Novatail.co</p>
              <a href="#" class="back-to-top" @click="scrollToTop">To the top</a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'AfricanAdventuresApp',
  data() {
    return {
      currentStep: 1,
      activeSection: 'hero',
      isScrolling: false,
      travelPlan: {
        destinations: [],
        duration: '',
        budgetIndex: 2,
        activities: [],
        name: '',
        email: '',
        dates: '',
        travelers: '',
        notes: ''
      },
      plannerDestinations: [
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
        { value: '1-week', label: '1 Week', icon: 'fas fa-calendar-week' },
        { value: '2-weeks', label: '2 Weeks', icon: 'fas fa-calendar-alt' },
        { value: '3-weeks', label: '3 Weeks', icon: 'fas fa-calendar' },
        { value: '1-month', label: '1 Month', icon: 'fas fa-calendar-plus' }
      ],
      budgetOptions: [
        { label: 'Budget', description: '$2,000 - $4,000 per person', range: '$2k-4k' },
        { label: 'Value', description: '$4,000 - $6,000 per person', range: '$4k-6k' },
        { label: 'Premium', description: '$6,000 - $10,000 per person', range: '$6k-10k' },
        { label: 'Luxury', description: '$10,000 - $15,000 per person', range: '$10k-15k' },
        { label: 'Ultra-Luxury', description: '$15,000+ per person', range: '$15k+' }
      ],
      activities: [
        { id: 'safari', name: 'Game Drives', icon: 'fas fa-binoculars' },
        { id: 'walking', name: 'Walking Safaris', icon: 'fas fa-hiking' },
        { id: 'photography', name: 'Photography', icon: 'fas fa-camera' },
        { id: 'diving', name: 'Scuba Diving', icon: 'fas fa-swimmer' },
        { id: 'cultural', name: 'Cultural Tours', icon: 'fas fa-users' },
        { id: 'birdwatching', name: 'Bird Watching', icon: 'fas fa-crow' },
        { id: 'conservation', name: 'Conservation', icon: 'fas fa-leaf' },
        { id: 'luxury', name: 'Luxury Experiences', icon: 'fas fa-gem' }
      ]
    }
  },
  mounted() {
    // Enhanced smooth scrolling for anchor links
    this.initializeScrolling();
    this.initializeScrollSpy();
    this.initializeScrollAnimations();
  },
  watch: {
    currentStep() {
      // Trigger fade-in animation for new steps
      this.$nextTick(() => {
        const currentStepEl = document.querySelector('.planner-step');
        if (currentStepEl) {
          currentStepEl.classList.add('fade-in');
        }
      });
    }
  },
  methods: {
    initializeScrolling() {
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', (e) => {
          e.preventDefault();
          const targetId = anchor.getAttribute('href').substring(1);
          const target = document.getElementById(targetId);
          
          if (target) {
            this.smoothScrollTo(target);
          }
        });
      });
    },

    initializeScrollSpy() {
      const sections = ['hero', 'destinations', 'wildlife', 'travel-planner', 'impact'];
      const navLinks = document.querySelectorAll('.nav-links a');
      
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            this.activeSection = entry.target.id || 'hero';
            
            // Update navigation active states
            navLinks.forEach(link => {
              const href = link.getAttribute('href');
              if (href === `#${this.activeSection}`) {
                link.classList.add('active');
              } else {
                link.classList.remove('active');
              }
            });
          }
        });
      }, { threshold: 0.3 });

      sections.forEach(id => {
        const element = document.getElementById(id) || document.querySelector('.hero-section');
        if (element) observer.observe(element);
      });
    },

    initializeScrollAnimations() {
      const animatedElements = document.querySelectorAll('.destination-card, .experience-item, .impact-stat');
      
      const animationObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('animate-in');
          }
        });
      }, { threshold: 0.1 });

      animatedElements.forEach(el => animationObserver.observe(el));
    },

    smoothScrollTo(target) {
      this.isScrolling = true;
      const targetPosition = target.offsetTop - 80; // Account for fixed nav
      const startPosition = window.pageYOffset;
      const distance = targetPosition - startPosition;
      const duration = 1000;
      let start = null;

      const step = (timestamp) => {
        if (!start) start = timestamp;
        const progress = timestamp - start;
        const ease = this.easeInOutCubic(progress / duration);
        
        window.scrollTo(0, startPosition + distance * ease);
        
        if (progress < duration) {
          window.requestAnimationFrame(step);
        } else {
          this.isScrolling = false;
        }
      };

      window.requestAnimationFrame(step);
    },

    easeInOutCubic(t) {
      return t < 0.5 ? 4 * t * t * t : (t - 1) * (2 * t - 2) * (2 * t - 2) + 1;
    },

    scrollToTop() {
      this.smoothScrollTo(document.querySelector('.hero-section'));
    },

    // Travel Planner Methods
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
        name: '',
        email: '',
        dates: '',
        travelers: '',
        notes: ''
      };
    },

    togglePlannerDestination(destinationId) {
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

    getPlannerDestination(id) {
      return this.plannerDestinations.find(dest => dest.id === id);
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
      // Simulate plan download
      alert('Your personalized African adventure itinerary will be sent to your email!');
    },

    contactExpert() {
      // Simulate expert contact
      alert('Our travel expert will contact you within 24 hours to discuss your African adventure!');
    }
  }
}
</script>