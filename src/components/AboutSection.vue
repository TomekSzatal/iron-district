
<template>
  <section id="o-klubie" class="about-section">
    <div class="container about-grid">
      <div class="about-visual">
        <img
          src="https://images.unsplash.com/photo-1534438327276-14e5300c3a48?auto=format&fit=crop&w=1100&q=85"
          alt="Wnętrze nowoczesnej siłowni"
          loading="lazy"
        />
        <div class="visual-frame"></div>
        <div class="experience-badge">
          <strong>100%</strong>
          <span>ZAANGAŻOWANIA</span>
        </div>
      </div>

      <div class="about-content">
        <div class="section-eyebrow">
          <span></span>
          POZNAJ IRON DISTRICT
        </div>

        <h2 class="section-title">
          NIE JESTEŚMY<br />
          ZWYKŁĄ <span class="accent">SIŁOWNIĄ.</span>
        </h2>

        <p class="lead">
          To miejsce dla ludzi, którzy nie szukają wymówek.
          Dla tych, którzy każdego dnia chcą być silniejsi
          niż wczoraj.
        </p>

        <p class="description">
          IRON DISTRICT to przestrzeń stworzona z pasji do
          treningu. Nowoczesny sprzęt, industrialny klimat
          i społeczność, która motywuje do działania.
          Niezależnie od poziomu zaawansowania, znajdziesz
          tutaj przestrzeń do rozwoju.
        </p>

        <div class="about-features">
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Profesjonalny sprzęt treningowy</span>
          </div>
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Trening dla każdego poziomu</span>
          </div>
          <div class="feature">
            <span class="feature-icon">✓</span>
            <span>Atmosfera bez kompromisów</span>
          </div>
        </div>

        <a href="#strefy" class="about-button">
          POZNAJ NASZE STREFY
          <span>↗</span>
        </a>
      </div>
    </div>

    <div class="container stats">
      <div class="stat">
        <strong>1200<span>m²</span></strong>
        <p>PRZESTRZENI TRENINGOWEJ</p>
      </div>
      <div class="stat">
        <strong>4</strong>
        <p>STREFY TRENINGOWE</p>
      </div>
      <div class="stat">
        <strong>24<span>/7</span></strong>
        <p>ENERGIA BEZ LIMITU</p>
      </div>
      <div class="stat">
        <strong>100<span>%</span></strong>
        <p>NASTAWIENIA NA PROGRES</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  padding: 120px 0 70px;
  background: #0c0c0c;
  overflow: hidden;
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 85px;
}

.about-visual {
  position: relative;
  height: 590px;
}

.about-visual img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(35%) brightness(0.8);
}

.visual-frame {
  position: absolute;
  inset: 20px -20px -20px 20px;
  border: 2px solid #ed2828;
  z-index: 0;
  pointer-events: none;
}

.about-visual img {
  position: relative;
  z-index: 1;
}

.experience-badge {
  position: absolute;
  z-index: 2;
  bottom: 25px;
  left: -25px;
  display: flex;
  flex-direction: column;
  gap: 5px;
  padding: 24px 30px;
  background: #ed2828;
}

.experience-badge strong {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 55px;
  line-height: 1;
}

.experience-badge span {
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1.5px;
}

.section-eyebrow {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 22px;
  color: #ff4545;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
}

.section-eyebrow span {
  width: 28px;
  height: 2px;
  background: #ff3434;
}

.about-content .section-title {
  margin: 0 0 30px;
  font-size: clamp(44px, 5vw, 72px);
}

.lead {
  margin-bottom: 20px;
  font-size: 18px;
  font-weight: 600;
  line-height: 1.8;
}

.description {
  color: #aaa;
  font-size: 14px;
  line-height: 2;
}

.about-features {
  display: grid;
  gap: 18px;
  margin: 30px 0 38px;
}

.feature {
  display: flex;
  align-items: center;
  gap: 13px;
  font-size: 14px;
  font-weight: 600;
}

.feature-icon {
  display: grid;
  place-items: center;
  width: 24px;
  height: 24px;
  background: #ed282825;
  color: #ff4545;
  font-weight: 900;
}

.about-button {
  display: inline-flex;
  align-items: center;
  gap: 25px;
  padding: 19px 26px;
  background: #ed2828;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 1px;
  transition: background 0.2s, transform 0.2s;
}

.about-button:hover {
  background: #c71f1f;
  transform: translateY(-3px);
}

.stats {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  margin-top: 120px;
  padding-top: 55px;
  border-top: 1px solid #292929;
}

.stat {
  text-align: center;
}

.stat strong {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: clamp(45px, 5vw, 70px);
  line-height: 1;
}

.stat strong span {
  color: #ff3434;
  font-size: 0.55em;
}

.stat p {
  margin-top: 12px;
  color: #aaa;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 1.2px;
}

@media (max-width: 900px) {
  .about-grid {
    grid-template-columns: 1fr;
    gap: 65px;
  }

  .about-visual {
    height: 450px;
    margin-right: 20px;
  }

  .stats {
    grid-template-columns: repeat(2, 1fr);
    gap: 40px;
    margin-top: 80px;
  }
}

@media (max-width: 550px) {
  .about-section {
    padding-top: 80px;
  }

  .about-visual {
    height: 350px;
    margin-left: 15px;
  }

  .experience-badge {
    left: -15px;
    padding: 15px 20px;
  }

  .experience-badge strong {
    font-size: 42px;
  }

  .about-content .section-title {
    font-size: 47px;
  }

  .stat p {
    font-size: 10px;
  }
}
</style>
