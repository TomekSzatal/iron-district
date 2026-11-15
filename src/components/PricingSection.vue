
<script setup lang="ts">
const plans = [
  {
    name: 'BASIC',
    price: '99',
    description: 'Idealny start dla osób, które chcą trenować regularnie.',
    features: [
      'Dostęp do strefy siłowej',
      'Dostęp do strefy cardio',
      'Szatnie i prysznice',
      'Trening w godzinach 6:00–22:00',
    ],
    featured: false,
  },
  {
    name: 'PRO',
    price: '149',
    description: 'Pełna swoboda i wszystkie możliwości IRON DISTRICT.',
    features: [
      'Wszystko z pakietu BASIC',
      'Dostęp do wszystkich stref',
      'Nielimitowany dostęp 24/7',
      'Zajęcia grupowe',
      'Konsultacja z trenerem',
    ],
    featured: true,
  },
  {
    name: 'ELITE',
    price: '229',
    description: 'Maksymalne wsparcie w osiąganiu ambitnych celów.',
    features: [
      'Wszystko z pakietu PRO',
      '2 treningi personalne miesięcznie',
      'Indywidualny plan treningowy',
      'Analiza postępów',
      'Priorytetowa rezerwacja zajęć',
    ],
    featured: false,
  },
]
</script>

<template>
  <section id="karnety" class="pricing-section">
    <div class="container">
      <div class="section-heading">
        <div class="eyebrow">
          <span></span>
          WYBIERZ SWÓJ POZIOM
        </div>

        <h2 class="section-title">
          TWOJA DROGA.<br />
          <span class="accent">TWÓJ KARNET.</span>
        </h2>

        <p>
          Bez zbędnych komplikacji. Wybierz pakiet,
          który najlepiej odpowiada Twoim celom.
        </p>
      </div>

      <div class="pricing-grid">
        <article
          v-for="plan in plans"
          :key="plan.name"
          class="plan-card"
          :class="{ featured: plan.featured }"
        >
          <div v-if="plan.featured" class="popular-badge">
            NAJCZĘŚCIEJ WYBIERANY
          </div>

          <div class="plan-header">
            <span class="plan-label">KARNET</span>
            <h3>{{ plan.name }}</h3>
            <p>{{ plan.description }}</p>
          </div>

          <div class="plan-price">
            <strong>{{ plan.price }}</strong>
            <div>
              <span>ZŁ</span>
              <small>/ MIESIĄC</small>
            </div>
          </div>

          <div class="price-divider"></div>

          <ul>
            <li v-for="feature in plan.features" :key="feature">
              <span class="check">✓</span>
              {{ feature }}
            </li>
          </ul>

          <a
            href="#kontakt"
            class="plan-button"
            :class="{ primary: plan.featured }"
          >
            WYBIERZ {{ plan.name }}
            <span>↗</span>
          </a>
        </article>
      </div>

      <p class="pricing-note">
        Ceny i pakiety są przykładowe. IRON DISTRICT to projekt
        demonstracyjny, a wybór karnetu nie stanowi zakupu.
      </p>
    </div>
  </section>
</template>

<style scoped>
.pricing-section {
  padding: 120px 0;
  background: #111;
}

.section-heading {
  text-align: center;
  margin-bottom: 65px;
}

.eyebrow {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin-bottom: 20px;
  color: #ff5555;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
}

.eyebrow span {
  width: 28px;
  height: 2px;
  background: #ff3434;
}

.section-title {
  margin: 0;
}

.section-heading > p {
  max-width: 480px;
  margin: 25px auto 0;
  color: #aaa;
  font-size: 14px;
  line-height: 1.8;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  align-items: stretch;
  gap: 24px;
}

.plan-card {
  position: relative;
  display: flex;
  flex-direction: column;
  padding: 38px 30px;
  border: 1px solid #333;
  background: #181818;
  transition: transform 0.3s, border-color 0.3s;
}

.plan-card:hover {
  transform: translateY(-7px);
  border-color: #ed2828;
}

.plan-card.featured {
  border: 2px solid #ed2828;
  background: linear-gradient(160deg, #251414, #181818 50%);
}

.popular-badge {
  position: absolute;
  top: -17px;
  left: 50%;
  transform: translateX(-50%);
  padding: 10px 18px;
  background: #ed2828;
  color: white;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 1px;
  white-space: nowrap;
}

.plan-label {
  color: #888;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 2px;
}

.plan-header h3 {
  margin: 10px 0 14px;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 49px;
  font-weight: 900;
  line-height: 1;
}

.plan-header p {
  min-height: 68px;
  color: #aaa;
  font-size: 13px;
  line-height: 1.8;
}

.plan-price {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: 20px;
}

.plan-price strong {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 85px;
  line-height: 1;
}

.plan-price > div {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.plan-price span {
  color: #ff4545;
  font-size: 22px;
  font-weight: 800;
}

.plan-price small {
  color: #888;
  font-size: 10px;
  font-weight: 700;
}

.price-divider {
  height: 1px;
  margin: 30px 0;
  background: #333;
}

ul {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin: 0 0 40px;
  padding: 0;
  list-style: none;
}

li {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  color: #ccc;
  font-size: 13px;
  line-height: 1.5;
}

.check {
  color: #ff4545;
  font-weight: 900;
}

.plan-button {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  min-height: 55px;
  margin-top: auto;
  padding: 0 20px;
  border: 1px solid #777;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 0.6px;
  transition: background 0.2s;
}

.plan-button:hover,
.plan-button.primary {
  border-color: #ed2828;
  background: #ed2828;
}

.plan-button.primary:hover {
  background: #c71f1f;
}

.pricing-note {
  margin-top: 35px;
  color: #888;
  font-size: 12px;
  line-height: 1.7;
  text-align: center;
}

@media (max-width: 950px) {
  .pricing-grid {
    grid-template-columns: 1fr;
    max-width: 520px;
    margin: 0 auto;
    gap: 40px;
  }

  .plan-header p {
    min-height: auto;
  }
}

@media (max-width: 650px) {
  .pricing-section {
    padding: 80px 0;
  }

  .section-title {
    font-size: 48px;
  }
}
</style>
