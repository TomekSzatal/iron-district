
<script setup lang="ts">
const trainers = [
  {
    name: 'ADAM KOWALSKI',
    role: 'TRENING SIŁOWY',
    number: '01',
    image: 'https://images.unsplash.com/photo-1567013127542-490d757e51fc?auto=format&fit=crop&w=800&q=85',
    description: 'Specjalista od budowania siły i sylwetki.',
  },
  {
    name: 'MARTA NOWAK',
    role: 'TRENING PERSONALNY',
    number: '02',
    image: 'https://images.unsplash.com/photo-1518611012118-696072aa579a?auto=format&fit=crop&w=800&q=85',
    description: 'Pomaga osiągać cele i budować dobre nawyki.',
  },
  {
    name: 'KAMIL WIŚNIEWSKI',
    role: 'BOX & CONDITIONING',
    number: '03',
    image: 'https://images.unsplash.com/photo-1517836357463-d25dfeac3438?auto=format&fit=crop&w=800&q=85',
    description: 'Trening wytrzymałości, dynamiki i charakteru.',
  },
]
</script>

<template>
  <section id="trenerzy" class="trainers-section">
    <div class="container">
      <div class="section-heading">
        <div class="eyebrow">
          <span></span>
          LUDZIE, KTÓRZY MOTYWUJĄ
        </div>

        <h2 class="section-title">
          POZNAJ NASZYCH<br />
          <span class="accent">TRENERÓW.</span>
        </h2>

        <p class="section-description">
          Doświadczenie, pasja i zaangażowanie.
          Poznaj zespół, który pomoże Ci wejść
          na wyższy poziom.
        </p>
      </div>

      <div class="trainers-grid">
        <article
          v-for="trainer in trainers"
          :key="trainer.number"
          class="trainer-card"
        >
          <div class="trainer-image">
            <img
              :src="trainer.image"
              :alt="`Zdjęcie ilustracyjne trenera — ${trainer.role}`"
              loading="lazy"
            />

            <div class="image-overlay"></div>
            <span class="trainer-number">{{ trainer.number }}</span>
          </div>

          <div class="trainer-info">
            <span class="trainer-role">{{ trainer.role }}</span>
            <h3>{{ trainer.name }}</h3>
            <p>{{ trainer.description }}</p>

            <a href="#kontakt">
              UMÓW TRENING <span>↗</span>
            </a>
          </div>
        </article>
      </div>

      <p class="demo-note">
        Projekt demonstracyjny — przedstawione profile trenerów są fikcyjne,
        a fotografie mają charakter ilustracyjny.
      </p>
    </div>
  </section>
</template>

<style scoped>
.trainers-section {
  padding: 120px 0;
  background: #0b0b0b;
}

.section-heading {
  text-align: center;
  margin-bottom: 55px;
}

.eyebrow {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
  margin-bottom: 22px;
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

.section-description {
  max-width: 540px;
  margin: 25px auto 0;
  color: #b7b7b7;
  font-size: 14px;
  line-height: 1.9;
}

.trainers-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 25px;
}

.trainer-card {
  background: #151515;
  border: 1px solid #292929;
  transition: transform 0.3s, border-color 0.3s;
}

.trainer-card:hover {
  transform: translateY(-8px);
  border-color: #ed2828;
}

.trainer-image {
  position: relative;
  height: 390px;
  overflow: hidden;
}

.trainer-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(75%);
  transition: transform 0.5s, filter 0.5s;
}

.trainer-card:hover .trainer-image img {
  transform: scale(1.06);
  filter: grayscale(0%);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(0deg, #151515, transparent 55%);
}

.trainer-number {
  position: absolute;
  top: 20px;
  left: 20px;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 28px;
  font-weight: 800;
  color: #fff;
}

.trainer-info {
  padding: 26px;
}

.trainer-role {
  color: #ff5555;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1.5px;
}

.trainer-info h3 {
  margin: 12px 0;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 34px;
  line-height: 1;
}

.trainer-info p {
  color: #aaa;
  font-size: 13px;
  line-height: 1.8;
}

.trainer-info a {
  display: inline-flex;
  align-items: center;
  gap: 15px;
  margin-top: 20px;
  color: #ff5555;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1px;
}

.trainer-info a:hover {
  color: white;
}

.demo-note {
  margin-top: 30px;
  color: #888;
  font-size: 12px;
  text-align: center;
  line-height: 1.7;
}

@media (max-width: 900px) {
  .trainers-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 650px) {
  .trainers-section {
    padding: 80px 0;
  }

  .trainers-grid {
    grid-template-columns: 1fr;
  }

  .trainer-image {
    height: 420px;
  }

  .section-title {
    font-size: 48px;
  }
}
</style>
