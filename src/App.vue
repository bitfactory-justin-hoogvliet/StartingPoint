<template>
  <div class="app">
    <!-- Navigation -->
    <NavigationBar @smooth-scroll="smoothScrollTo" />

    <!-- Hero Section -->
    <HeroSection />

    <!-- Quick Links -->
    <QuickLinks @smooth-scroll="smoothScrollTo" />

    <!-- Key Destinations -->
    <DestinationsSection />

    <!-- Wildlife Experiences -->
    <ExperiencesSection />

    <!-- Testimonials Section -->
    <TestimonialsSection />

    <!-- Travel Plan Generator -->
    <TravelPlannerSection />

    <!-- Impact Section -->
    <ImpactSection />

    <!-- Footer -->
    <FooterSection @smooth-scroll="smoothScrollTo" @scroll-to-top="scrollToTop" />
  </div>
</template>

<script>
import NavigationBar from './components/NavigationBar.vue'
import HeroSection from './components/HeroSection.vue'
import QuickLinks from './components/QuickLinks.vue'
import DestinationsSection from './components/DestinationsSection.vue'
import ExperiencesSection from './components/ExperiencesSection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import TravelPlannerSection from './components/TravelPlannerSection.vue'
import ImpactSection from './components/ImpactSection.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  name: 'AfricanAdventuresApp',
  components: {
    NavigationBar,
    HeroSection,
    QuickLinks,
    DestinationsSection,
    ExperiencesSection,
    TestimonialsSection,
    TravelPlannerSection,
    ImpactSection,
    FooterSection
  },
  data() {
    return {
      activeSection: 'hero',
      isScrolling: false
    }
  },
  mounted() {
    // Enhanced smooth scrolling for anchor links
    this.initializeScrollSpy();
    this.initializeScrollAnimations();
  },
  methods: {
    initializeScrollSpy() {
      const sections = ['hero', 'destinations', 'wildlife', 'testimonials', 'travel-planner', 'impact'];
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
    }
  }
}
</script>