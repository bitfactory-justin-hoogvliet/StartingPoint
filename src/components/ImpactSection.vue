<template>
  <section id="impact" class="impact-section">
    <div class="container">
      <h2 class="section-title">Reis verantwoord</h2>
      <p class="section-intro">
        Terwijl jij van je droomreis geniet, draag je bij aan de ontwikkeling van lokale community's, economieën en de omgeving. 
        Dat voelt goed! We werken samen met lokale partners om ervoor te zorgen dat toerisme ten goede komt aan de gemeenschappen die je bezoekt.
      </p>

      <div class="impact-stats">
        <div v-for="stat in stats" :key="stat.label" class="impact-stat">
          <div class="stat-number">{{ stat.number }}</div>
          <div class="stat-label">{{ stat.label }}</div>
        </div>
      </div>

      <div class="impact-description">
        <p>
          Meer dan 400 reizigers zijn fan van onze persoonlijke aanpak, authentieke plekken en flexibiliteit. 
          Je geld staat veilig bij Stichting Veilig Verzekerd Op Reis tot vlak voor vertrek, wat er ook gebeurt. 
          Al meer dan 10 jaar ontwikkelen we reizen in Afrika voor families, vriendengroepen en lovebirds.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ImpactSection',
  data() {
    return {
      stats: [
        { number: '4.8', label: 'Google reviews' },
        { number: '100%', label: 'Financieel beschermd' },
        { number: '5.000+', label: 'Tevreden reizigers' },
        { number: '10+', label: 'Jaren ervaring' }
      ]
    }
  }
}
</script>
