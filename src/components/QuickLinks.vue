<template>
  <section class="quick-links">
    <div class="container">
      <h2>Avontuurlijke en unieke reizen in Afrika</h2>
      <div class="links-grid">
        <a href="#destinations" class="quick-link">Onze bestemmingen</a>
        <a href="#wildlife" class="quick-link">Charlie's way of traveling</a>
        <a href="#travel-planner" class="quick-link">Op maat gemaakt</a>
        <a href="#impact" class="quick-link">Reizen met impact</a>
        <a href="#testimonials" class="quick-link">Reizigers aan het woord</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'QuickLinks',
  mounted() {
    this.initializeQuickLinks();
  },
  methods: {
    initializeQuickLinks() {
      document.querySelectorAll('.quick-link').forEach(link => {
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
