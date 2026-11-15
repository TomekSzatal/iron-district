
<script setup lang="ts">
const zones = [
  {
    number: '01',
    name: 'STREFA SIŁOWA',
    description: 'Wolne ciężary, profesjonalne maszyny i przestrzeń do budowania prawdziwej siły.',
    image: 'https://images.unsplash.com/photo-1534438327276-14e5300c3a48?auto=format&fit=crop&w=1000&q=85',
    tag: 'SIŁA',
  },
  {
    number: '02',
    name: 'STREFA CARDIO',
    description: 'Nowoczesne urządzenia do poprawy kondycji, wytrzymałości i spalania kalorii.',
    image: 'https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?auto=format&fit=crop&w=1000&q=85',
    tag: 'WYTRZYMAŁOŚĆ',
  },
  {
    number: '03',
    name: 'TRENING FUNKCJONALNY',
    description: 'Trening całego ciała, mobilność, dynamika i rozwijanie sprawności.',
    image: 'https://images.unsplash.com/photo-1517836357463-d25dfeac3438?auto=format&fit=crop&w=1000&q=85',
    tag: 'SPRAWNOŚĆ',
  },
  {
    number: '04',
    name: 'STREFA BOX',
    description: 'Miejsce na intensywny trening, technikę i przekraczanie własnych granic.',
    image: 'https://images.unsplash.com/photo-1549719386-74dfcbf7dbed?auto=format&fit=crop&w=1000&q=85',
    tag: 'CHARAKTER',
  },
]
</script>

<template>
  <section id="strefy" class="zones-section">
    <div class="container">
      <div class="section-heading">
        <div>
          <div class="eyebrow">
            <span></span>
            TRENUJ NA SWOICH ZASADACH
          </div>
          <h2 class="section-title">
            TWOJA PRZESTRZEŃ.<br />
            <span class="accent">TWOJE MOŻLIWOŚCI.</span>
          </h2>
        </div>

        <p>
          Cztery strefy. Jeden cel — progres.
          Znajdź przestrzeń, która pasuje do
          Twojego stylu treningu.
        </p>
      </div>

      <div class="zones-grid">
        <article
          v-for="zone in zones"
          :key="zone.number"
          class="zone-card"
        >
          <img :src="zone.image" :alt="zone.name" loading="lazy" />

          <div class="card-overlay"></div>

          <span class="zone-number">{{ zone.number }}</span>
          <span class="zone-tag">{{ zone.tag }}</span>

          <div class="zone-content">
            <h3>{{ zone.name }}</h3>
            <p>{{ zone.description }}</p>
            <a href="#kontakt" :aria-label="`Zapytaj o ${zone.name}`">
              DOWIEDZ SIĘ WIĘCEJ <span>↗</span>
            </a>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>
.zones-section {
  padding: 115px 0 125px;
  background: #111;
}

.section-heading {
  display: flex;
  justify-content: space-between;
  align-items: end;
  gap: 35px;
  margin-bottom: 45px;
}

.eyebrow {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 22px;
  color: #ff4545;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
}

.eyebrow span {
  width: 28px;
  height: 2px;
  background: #ff3434;
}

.section-heading .section-title {
  margin: 0;
}

.section-heading > p {
  max-width: 285px;
  color: #aaa;
  font-size: 14px;
  line-height: 1.9;
}

.zones-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 22px;
}

.zone-card {
  position: relative;
  min-height: 430px;
  overflow: hidden;
  background: #1b1b1b;
}

.zone-card img {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(30%) brightness(0.75);
  transition: transform 0.6s ease, filter 0.6s ease;
}

.zone-card:hover img {
  transform: scale(1.08);
  filter: grayscale(0%) brightness(0.9);
}

.card-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    0deg,
    #050505f5 0%,
    #05050570 45%,
    #05050530 100%
  );
}

.zone-number {
  position: absolute;
  top: 25px;
  left: 28px;
  color: #ffffffa8;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 24px;
  font-weight: 700;
}

.zone-tag {
  position: absolute;
  top: 28px;
  right: 28px;
  padding: 9px 12px;
  background: #ed2828;
  color: white;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 1px;
}

.zone-content {
  position: absolute;
  bottom: 30px;
  left: 30px;
  right: 30px;
}

.zone-content h3 {
  margin: 0 0 12px;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: clamp(30px, 4vw, 43px);
  font-weight: 900;
  line-height: 1;
}

.zone-content p {
  max-width: 380px;
  color: #ccc;
  font-size: 13px;
  line-height: 1.8;
}

.zone-content a {
  display: inline-flex;
  align-items: center;
  gap: 15px;
  margin-top: 13px;
  color: #ff5555;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1px;
}

.zone-content a:hover {
  color: white;
}

@media (max-width: 800px) {
  .section-heading {
    flex-direction: column;
    align-items: start;
  }

  .section-heading > p {
    max-width: 520px;
  }
}

@media (max-width: 650px) {
  .zones-section {
    padding: 80px 0;
  }

  .zones-grid {
    grid-template-columns: 1fr;
  }

  .zone-card {
    min-height: 400px;
  }

  .zone-content {
    left: 22px;
    right: 22px;
    bottom: 25px;
  }

  .section-heading .section-title {
    font-size: 46px;
  }
}
</style>
