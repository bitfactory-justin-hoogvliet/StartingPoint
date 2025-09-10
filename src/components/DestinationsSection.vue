<template>
  <section id="destinations" class="destinations-section">
    <div class="container">
      <h2 class="section-title">Onze bestemmingen</h2>
      <p class="section-intro">
        Weet je al welk land jij wilt ontdekken? Van de uitgestrekte savannes van Kenia tot de adembenemende duinen van Namibië, 
        van de ongerepte stranden van Mozambique tot de indrukwekkende berglandschappen van Rwanda. Elk land heeft zijn eigen unieke charme 
        en onvergetelijke ervaringen die wachten om ontdekt te worden.
      </p>

      <div class="destinations-grid">
        <div v-for="destination in destinations" :key="destination.id" class="destination-card">
          <div class="destination-image" :style="`background-image: url('${destination.image}')`"></div>
          <div class="destination-content">
            <h3>{{ destination.name }}</h3>
            <div class="destination-type">{{ destination.type }}</div>
            <p class="destination-description">
              {{ destination.description }}
            </p>
            <div class="destination-highlight">
              <strong>{{ destination.highlightLabel }}:</strong> {{ destination.highlight }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'DestinationsSection',
  data() {
    return {
      destinations: [
        {
          id: 'kenia',
          name: 'Kenia',
          type: 'Oostelijk Afrika',
          image: './images/kruger-national-park3.jpeg',
          description: 'Ontdek de ongerepte wildernis van Kenia. Van de Great Migration in de Masai Mara tot het wandelen met Masai-krijgers, Kenia biedt authentieke safari-ervaringen.',
          highlightLabel: 'Ervaring',
          highlight: 'Hike met de Masai en beleef de Great Migration van dichtbij.'
        },
        {
          id: 'zuid-afrika',
          name: 'Zuid-Afrika',
          type: 'Zuidelijk Afrika',
          image: './images/aa-Hluhluwe-lion.jpeg',
          description: 'Van de Big Five in Kruger National Park tot de prachtige wijnlanden van Stellenbosch. Zuid-Afrika combineert wildlife, cultuur en avontuur.',
          highlightLabel: 'Hoogtepunt',
          highlight: 'Big Five safari\'s en diverse landschappen in één land.'
        },
        {
          id: 'namibie',
          name: 'Namibië',
          type: 'Zuidelijk Afrika',
          image: './images/klaserie-private-game-reserve.jpg',
          description: 'Verken de mystieke Sossusvlei duinen en de wilde Skeleton Coast. Namibië biedt unieke woestijnlandschappen en onvergetelijke zonsondergangen.',
          highlightLabel: 'Uniek',
          highlight: 'De hoogste zandduinen ter wereld en sterrenrijke nachten.'
        },
        {
          id: 'botswana',
          name: 'Botswana',
          type: 'Zuidelijk Afrika',
          image: './images/Landenpagina-Botswana-leeuw-Chobe-Emiel-Kusters-800x500-1.jpg',
          description: 'Ontdek de pristine wildernis van de Okavango Delta en spot olifanten in Chobe National Park. Botswana is het paradijs voor echte natuurliefhebbers.',
          highlightLabel: 'Wildlife',
          highlight: 'Meer dan 120,000 olifanten en exclusieve mokoro-tochten.'
        },
        {
          id: 'tanzania',
          name: 'Tanzania',
          type: 'Oostelijk Afrika',
          image: './images/diving-south-africa-sodwana-bay-anna-reef.jpg',
          description: 'Beklim de Kilimanjaro, ervaar de Serengeti en ontspan op Zanzibar\'s witte stranden. Tanzania combineert avontuur met paradijselijke kustlijnen.',
          highlightLabel: 'Avontuur',
          highlight: 'Van Afrika\'s hoogste berg tot pristine koraalriffen.'
        },
        {
          id: 'oeganda',
          name: 'Oeganda',
          type: 'Oostelijk Afrika',
          image: './images/Kopie-van-Blyde-River-Canyon.jpg',
          description: 'De parel van Afrika biedt gorilla tracking, chimpanzee trekking en ongelooflijke biodiversiteit. Ontmoet de vriendelijkste mensen van het continent.',
          highlightLabel: 'Uniek',
          highlight: 'Berggorilla\'s in hun natuurlijke habitat en gastvrije locals.'
        }
      ]
    }
  }
}
</script>
