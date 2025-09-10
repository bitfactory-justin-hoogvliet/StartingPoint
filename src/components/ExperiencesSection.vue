<template>
  <section id="wildlife" class="experiences-section">
    <div class="container">
      <h2 class="section-title">Charlie's way of traveling</h2>
      
      <div class="experience-timeline">
        <div v-for="(experience, index) in experiences" :key="experience.id" 
             class="experience-item" :class="{ reverse: index % 2 === 1 }">
          <div class="experience-image" :style="`background-image: url('${experience.image}')`"></div>
          <div class="experience-content">
            <h3>{{ experience.title }}</h3>
            <div class="experience-type">{{ experience.type }}</div>
            <p>{{ experience.description }}</p>
            <div class="experience-stats">
              <div v-for="stat in experience.stats" :key="stat.label" class="stat">
                <span class="stat-number">{{ stat.number }}</span>
                <span class="stat-label">{{ stat.label }}</span>
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
  name: 'ExperiencesSection',
  data() {
    return {
      experiences: [
        {
          id: 'home',
          title: '1. Afrika is ons thuis',
          type: 'Lokale expertise',
          image: './images/AA-Ezulwini-Valley.jpeg',
          description: 'We kennen het tot in de verste uithoeken en dat levert te gekke reizen op. Die stellen we samen door er zelf op uit te trekken. Geloof ons nou maar: deze reiservaringen vind je nergens anders!',
          stats: [
            { number: '10+ jaar', label: 'Ervaring' },
            { number: '100%', label: 'Lokaal team' }
          ]
        },
        {
          id: 'local',
          title: '2. Lokale ervaringen',
          type: 'Authentieke ontmoetingen',
          image: './images/Ezulwini-Valley2.jpeg',
          description: 'Dat betekent dat je op de plekken van de lokale bevolking komt. Hike met de Masai, kook met je gastfamilie in je homestay en sla een hengel uit met traditionele vissers.',
          stats: [
            { number: 'Unieke', label: 'Ervaringen' },
            { number: 'Lokale', label: 'Partners' }
          ]
        },
        {
          id: 'custom',
          title: '3. Op maat gemaakt',
          type: 'Jouw perfecte reis',
          image: './images/Kosi-Bay1.jpeg',
          description: 'Dus, waar heb je zin in? We stemmen de volledige reis op jouw wensen af. Onderweg kun je altijd op ons rekenen. Ook in het holst van de nacht.',
          stats: [
            { number: '24/7', label: 'Support' },
            { number: '100%', label: 'Op maat' }
          ]
        }
      ]
    }
  }
}
</script>
