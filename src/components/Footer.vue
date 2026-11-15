
<script setup lang="ts">
const year = new Date().getFullYear()
</script>

<template>
  <footer class="footer">
    <div class="container footer-main">
      <div class="footer-brand">
        <a href="#start" class="logo">
          IRON<span>DISTRICT</span>.
        </a>

        <p>
          Przekraczaj własne granice.
          Trenuj na swoich zasadach.
        </p>

        <span class="demo-label">
          PROJEKT DEMONSTRACYJNY
        </span>
      </div>

      <div class="footer-column">
        <h4>ODKRYJ KLUB</h4>
        <a href="#o-klubie">O klubie</a>
        <a href="#strefy">Strefy treningowe</a>
        <a href="#trenerzy">Trenerzy</a>
        <a href="#karnety">Karnety</a>
      </div>

      <div class="footer-column">
        <h4>INFORMACJE</h4>
        <a href="#opinie">Opinie demonstracyjne</a>
        <a href="#faq">FAQ</a>
        <a href="#kontakt">Kontakt demo</a>
      </div>

      <div class="footer-column">
        <h4>PROJEKT</h4>
        <p>
          Koncept strony klubu fitness
          przygotowany jako realizacja
          demonstracyjna do portfolio.
        </p>
        <a
          href="https://tovexastudio.netlify.app/"
          target="_blank"
          rel="noopener noreferrer"
          class="studio-link"
        >
          TOVEXA STUDIO ↗
        </a>
      </div>
    </div>

    <div class="container footer-bottom">
      <span>© {{ year }} IRON DISTRICT — PROJEKT DEMO</span>
      <span>DESIGN & DEVELOPMENT: TOVEXA STUDIO</span>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  padding: 80px 0 25px;
  border-top: 1px solid #292929;
  background: #080808;
}

.footer-main {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1fr;
  gap: 45px;
  padding-bottom: 70px;
}

.logo {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 31px;
  font-weight: 900;
}

.logo span {
  color: #ff3434;
}

.footer-brand > p {
  max-width: 290px;
  margin: 22px 0;
  color: #aaa;
  font-size: 13px;
  line-height: 1.9;
}

.demo-label {
  display: inline-block;
  padding: 9px 12px;
  border: 1px solid #555;
  color: #ccc;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 1px;
}

.footer-column {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 15px;
}

.footer-column h4 {
  margin: 0 0 10px;
  font-size: 12px;
  letter-spacing: 1px;
}

.footer-column a,
.footer-column p {
  margin: 0;
  color: #aaa;
  font-size: 13px;
  line-height: 1.8;
}

.footer-column a:hover {
  color: #ff5555;
}

.footer-column .studio-link {
  color: #ff5555;
  font-weight: 800;
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  padding-top: 25px;
  border-top: 1px solid #292929;
  color: #888;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 1px;
}

@media (max-width: 900px) {
  .footer-main {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 550px) {
  .footer-main {
    grid-template-columns: 1fr;
    gap: 35px;
  }

  .footer-bottom {
    flex-direction: column;
    line-height: 1.7;
  }
}
</style>
