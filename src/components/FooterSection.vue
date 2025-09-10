<template>
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
</template>

<script>
export default {
  name: 'FooterSection',
  mounted() {
    this.initializeFooterLinks();
  },
  methods: {
    initializeFooterLinks() {
      document.querySelectorAll('.footer-links a').forEach(link => {
        link.addEventListener('click', (e) => {
          e.preventDefault();
          const targetId = link.getAttribute('href').substring(1);
          const target = document.getElementById(targetId);
          
          if (target) {
            this.$emit('smooth-scroll', target);
          }
        });
      });
    },
    scrollToTop() {
      this.$emit('scroll-to-top');
    }
  }
}
</script>
