
<template>
  <section id="start" class="hero">
    <div class="hero-overlay"></div>

    <div class="container hero-content">
      <div class="eyebrow">
        <span class="line"></span>
        TWOJA SIŁA. TWOJE ZASADY.
      </div>

      <h1>
        PRZEKRACZAJ<br />
        <span>WŁASNE</span><br />
        GRANICE.
      </h1>

      <p>
        Nie przychodzisz tutaj być przeciętnym.
        Trenuj mocniej, buduj charakter i odkryj
        swoją najlepszą wersję w IRON DISTRICT.
      </p>

      <div class="hero-actions">
        <a href="#karnety" class="btn-primary">
          SPRAWDŹ KARNETY <span>↗</span>
        </a>
        <a href="#o-klubie" class="btn-outline">
          POZNAJ NASZ KLUB
        </a>
      </div>

      <p class="demo-banner">
        Projekt demonstracyjny wykonany przez Tovexa Studio.
        Klub, oferta i dane są fikcyjne.
      </p>

      <div class="hero-bottom">
        <div>
          <strong>01 / 03</strong>
          <span>WIĘCEJ NIŻ SIŁOWNIA</span>
        </div>
        <a href="#o-klubie">ODKRYJ WIĘCEJ ↓</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 820px;
  min-height: 100svh;
  display: flex;
  align-items: center;
  overflow: hidden;
  background:
    linear-gradient(90deg, #080808 0%, #080808e8 35%, #08080855 100%),
    url('https://images.unsplash.com/photo-1534438327276-14e5300c3a48?auto=format&fit=crop&w=1920&q=85')
    center / cover no-repeat;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(0deg, #090909 0%, transparent 30%);
  pointer-events: none;
}

.hero-content {
  position: relative;
  z-index: 1;
  padding-top: 150px;
  padding-bottom: 110px;
}

.eyebrow {
  display: flex;
  align-items: center;
  gap: 14px;
  color: #ff5555;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 3px;
}

.line {
  width: 35px;
  height: 2px;
  background: #ff3434;
}

h1 {
  margin: 30px 0;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: clamp(76px, 11vw, 164px);
  font-weight: 900;
  line-height: 0.78;
  letter-spacing: -2px;
}

h1 span {
  color: #ff3434;
}

.hero-content > p {
  max-width: 510px;
  color: #c4c4c4;
  font-size: 15px;
  line-height: 1.9;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
  margin-top: 35px;
}

.btn-primary,
.btn-outline {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 24px;
  min-height: 56px;
  padding: 0 25px;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 1px;
}

.btn-primary {
  background: #ed2828;
  color: white;
}

.btn-primary:hover {
  background: #bf2020;
}

.btn-outline {
  border: 1px solid #777;
}

.btn-outline:hover {
  border-color: #fff;
}

.hero-bottom {
  display: flex;
  justify-content: space-between;
  align-items: end;
  gap: 20px;
  margin-top: 65px;
  color: #aaa;
  font-size: 11px;
  letter-spacing: 1px;
}

.hero-bottom > div {
  display: flex;
  flex-direction: column;
  gap: 7px;
}

.hero-bottom strong {
  color: white;
  font-size: 17px;
}

@media (max-width: 700px) {
  .hero {
    min-height: 760px;
    background-position: 62% center;
  }

  .hero-content {
    padding-top: 160px;
    padding-bottom: 65px;
  }

  h1 {
    font-size: clamp(62px, 14vw, 95px);
    letter-spacing: -1px;
  }

  .hero-content > p {
    font-size: 14px;
  }

  .hero-bottom {
    margin-top: 75px;
  }
}
.hero-content > .demo-banner {
  max-width: 510px;
  margin-top: 24px;
  color: #bdbdbd;
  font-size: 13px;
  line-height: 1.7;
}
</style>
