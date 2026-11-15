
<script setup lang="ts">
const testimonials = [
  {
    text: 'Świetny klimat, profesjonalny sprzęt i przestrzeń, która motywuje do działania.',
    name: 'PRZYKŁADOWA OPINIA 01',
    category: 'TRENING SIŁOWY',
  },
  {
    text: 'Miejsce stworzone dla osób, które chcą trenować na własnych zasadach.',
    name: 'PRZYKŁADOWA OPINIA 02',
    category: 'TRENING FUNKCJONALNY',
  },
  {
    text: 'Nowoczesne wnętrze, świetna organizacja stref i mocna energia podczas każdego treningu.',
    name: 'PRZYKŁADOWA OPINIA 03',
    category: 'TRENING PERSONALNY',
  },
]
</script>

<template>
  <section id="opinie" class="testimonials-section">
    <div class="container">
      <div class="heading">
        <div class="eyebrow">SPOŁECZNOŚĆ IRON DISTRICT</div>
        <h2 class="section-title">
          SIŁA NASZEJ <span class="accent">SPOŁECZNOŚCI.</span>
        </h2>
        <p>
          Przykładowa prezentacja opinii klientów.
          Wszystkie poniższe wypowiedzi są fikcyjne.
        </p>
      </div>

      <div class="testimonials-grid">
        <article
          v-for="(review, index) in testimonials"
          :key="index"
          class="review-card"
        >
          <div class="stars" aria-label="Pięć gwiazdek">
            ★★★★★
          </div>

          <div class="quote-mark">“</div>

          <blockquote>{{ review.text }}</blockquote>

          <div class="review-author">
            <div class="avatar">{{ index + 1 }}</div>
            <div>
              <strong>{{ review.name }}</strong>
              <span>{{ review.category }}</span>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>
.testimonials-section {
  padding: 115px 0;
  background: #0b0b0b;
}

.heading {
  max-width: 850px;
  margin: 0 auto 55px;
  text-align: center;
}

.eyebrow {
  margin-bottom: 20px;
  color: #ff5555;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
}

.section-title {
  margin: 0;
}

.heading p {
  max-width: 570px;
  margin: 25px auto 0;
  color: #aaa;
  font-size: 14px;
  line-height: 1.8;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.review-card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-height: 315px;
  padding: 32px;
  border: 1px solid #303030;
  background: #161616;
  transition: transform .3s, border-color .3s;
}

.review-card:hover {
  transform: translateY(-6px);
  border-color: #ed2828;
}

.stars {
  color: #ff4545;
  letter-spacing: 5px;
  font-size: 17px;
}

.quote-mark {
  position: absolute;
  right: 25px;
  top: 25px;
  color: #ff343430;
  font-family: Georgia, serif;
  font-size: 100px;
  line-height: 1;
}

blockquote {
  margin: 28px 0 35px;
  color: #ddd;
  font-size: 15px;
  line-height: 1.9;
  flex: 1;
}

.review-author {
  display: flex;
  align-items: center;
  gap: 15px;
  padding-top: 22px;
  border-top: 1px solid #333;
}

.avatar {
  display: grid;
  place-items: center;
  width: 43px;
  height: 43px;
  background: #ed2828;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 24px;
  font-weight: 800;
}

.review-author strong {
  display: block;
  font-size: 11px;
  letter-spacing: .6px;
}

.review-author span {
  display: block;
  margin-top: 6px;
  color: #aaa;
  font-size: 10px;
}

@media (max-width: 900px) {
  .testimonials-grid {
    grid-template-columns: 1fr;
    max-width: 600px;
    margin: auto;
  }

  .review-card {
    min-height: auto;
  }
}

@media (max-width: 650px) {
  .testimonials-section {
    padding: 80px 0;
  }

  .section-title {
    font-size: 46px;
  }
}
</style>
