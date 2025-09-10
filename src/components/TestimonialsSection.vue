<template>
  <section id="testimonials" class="testimonials-section">
    <div class="container">
      <h2 class="section-title">Proef de avonturen van andere reizigers</h2>
      <p class="section-intro">
        Ontdek waarom meer dan 5.000 reizigers hun Afrika-avontuur aan ons toevertrouwen. 
        Lees hun verhalen en laat je inspireren voor jouw eigen onvergetelijke reis.
      </p>

      <div class="testimonials-grid">
        <div v-for="testimonial in testimonials" :key="testimonial.id" class="testimonial-card">
          <div class="testimonial-content">
            <div class="testimonial-text">
              "{{ testimonial.text }}"
            </div>
            <div class="testimonial-details">
              <div class="testimonial-author">{{ testimonial.author }}</div>
              <div class="testimonial-trip">{{ testimonial.tripType }}</div>
              <div class="testimonial-destinations">{{ testimonial.destinations }}</div>
            </div>
          </div>
        </div>
      </div>

      <div class="cta-section">
        <h3>Met wie ga jij op pad?</h3>
        <p>Tijd om de randjes van je comfortzone op te zoeken! Stap met je gezin in een 4x4 en tuur naar de stampende olifanten in Kenia, ga met je vrienden op een overnight hike in eSwatini of verken met je partner de duinen van de Sossusvlei samen met lokale gids Boesman.</p>
        
        <div class="travel-types">
          <div v-for="type in travelTypes" :key="type.id" class="travel-type-card">
            <div class="travel-type-icon">
              <i :class="type.icon"></i>
            </div>
            <h4>{{ type.name }}</h4>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TestimonialsSection',
  data() {
    return {
      testimonials: [
        {
          id: 1,
          text: "Wat een fantastische huwelijksreis hebben we gehad met Charlie's Travels! In slechts 19 dagen bezochten we drie landen: Zuid-Afrika, Swaziland en Mozambique. We hebben een paar nachten onder de sterrenhemel geslapen in onze persoonlijke camper en een paar nachten in luxe accommodaties. Alles was geweldig georganiseerd!",
          author: "Martin",
          tripType: "Lovebirds",
          destinations: "eSwatini, Mozambique, Zuid-Afrika"
        },
        {
          id: 2,
          text: "Onze zelfrijdende reis door Namibië en Botswana was een geweldige ervaring. We hebben genoten van de professionele communicatie van Charlie's Travels voor, tijdens en na onze reis. Ze zijn duidelijk een ervaren reisagent en kennen de markt goed.",
          author: "Steve",
          tripType: "Familiereis",
          destinations: "Botswana, Namibië"
        },
        {
          id: 3,
          text: "We zijn met de familie naar Zuid-Afrika gegaan en dat was fantastisch! Met onze input en wensen. Anna heeft aan een half woord genoeg en kent de regio's en accommodaties goed. We zouden onze volgende reis naar Afrika weer met Charlie's regelen!",
          author: "Leonie",
          tripType: "Familiereis",
          destinations: "Zuid-Afrika"
        },
        {
          id: 4,
          text: "Begin juli hebben wij een prachtige reis gemaakt naar Oeganda. Charlie's Travels heeft er een ongelooflijke ervaring van gemaakt. Oeganda heeft alles om van jouw reis iets onvergetelijk te maken: prachtige natuur, zoveel mooie wilde dieren, super lekker eten, de mensen zijn er ZO lief en vriendelijk, we kunnen het dan ook alleen maar aanraden!",
          author: "Domien",
          tripType: "Familiereis",
          destinations: "Oeganda"
        },
        {
          id: 5,
          text: "We hebben een heel fijne vakantie gehad met Charlie's in Tanzania. Het was echt off the beaten track, precies zoals we wilden. Perfect georganiseerd. Mooie mensen, leuke excursies, ik wil terug!",
          author: "Bas",
          tripType: "Lovebirds",
          destinations: "Tanzania"
        },
        {
          id: 6,
          text: "De gaafste ervaring van al mijn reizen tot nu toe! We zijn op plekken in Kenia geweest waar je nooit al 'gewone toerist' zou komen. Wij gaan zeker nog een keer met Charlie's op pad!",
          author: "Joost",
          tripType: "Vriendenreis",
          destinations: "Kenia"
        }
      ],
      travelTypes: [
        { id: 'lustrumreis', name: 'Lustrumreis', icon: 'fas fa-graduation-cap' },
        { id: 'familiereis', name: 'Familiereis', icon: 'fas fa-users' },
        { id: 'lovebirds', name: 'Lovebirds', icon: 'fas fa-heart' },
        { id: 'vriendenreis', name: 'Vriendenreis', icon: 'fas fa-user-friends' },
        { id: 'groepsreis', name: 'Groepsreis', icon: 'fas fa-people-group' }
      ]
    }
  }
}
</script>
