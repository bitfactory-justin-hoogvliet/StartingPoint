<template>
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
</template>

<script>
export default {
  name: 'NavigationBar',
  mounted() {
    this.initializeNavigation();
  },
  methods: {
    initializeNavigation() {
      // Initialize navigation event handlers
      const navLinks = document.querySelectorAll('.nav-links a');
      
      // Add click event listeners for smooth scrolling
      navLinks.forEach(link => {
        link.addEventListener('click', (e) => {
          e.preventDefault();
          const targetId = link.getAttribute('href').substring(1);
          const target = document.getElementById(targetId);
          
          if (target) {
            this.$emit('smooth-scroll', target);
          }
        });
      });
    }
  }
}
</script>
