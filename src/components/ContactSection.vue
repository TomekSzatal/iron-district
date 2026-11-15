
<script setup lang="ts">
import { ref } from 'vue'

const selectedPlan = ref('')
const submitted = ref(false)

function submitDemo() {
  submitted.value = true
}
</script>

<template>
  <section id="kontakt" class="contact-section">
    <div class="container contact-layout">
      <div class="contact-content">
        <div class="eyebrow">CZAS NA TWÓJ RUCH</div>

        <h2 class="section-title">
          GOTOWY NA<br />
          <span class="accent">ZMIANĘ?</span>
        </h2>

        <p>
          Pierwszy krok zaczyna się od decyzji.
          Sprawdź, jak wyglądałby proces zapisania
          się do IRON DISTRICT.
        </p>

        <div class="contact-info">
          <div class="info-item">
            <span>01</span>
            <div>
              <strong>WYBIERZ KARNET</strong>
              <p>Dopasuj pakiet do swojego stylu treningu.</p>
            </div>
          </div>

          <div class="info-item">
            <span>02</span>
            <div>
              <strong>WYPEŁNIJ FORMULARZ</strong>
              <p>Przetestuj demonstracyjny proces kontaktu.</p>
            </div>
          </div>

          <div class="info-item">
            <span>03</span>
            <div>
              <strong>ZACZNIJ DZIAŁAĆ</strong>
              <p>W prawdziwym klubie otrzymałbyś dalsze informacje.</p>
            </div>
          </div>
        </div>
      </div>

      <div class="contact-form-wrapper">
        <div class="form-header">
          <span>FORMULARZ DEMONSTRACYJNY</span>
          <h3>DOŁĄCZ DO NAS.</h3>
          <p>
            Formularz nie wysyła danych ani nie zapisuje
            na prawdziwy karnet.
          </p>
        </div>

        <form v-if="!submitted" @submit.prevent="submitDemo">
          <label for="demo-name">IMIĘ I NAZWISKO</label>
          <input
            id="demo-name"
            type="text"
            placeholder="Przykładowe imię"
            autocomplete="off"
            required
          />

          <label for="demo-email">ADRES E-MAIL</label>
          <input
            id="demo-email"
            type="email"
            placeholder="przyklad@example.com"
            autocomplete="off"
            required
          />

          <label for="demo-plan">WYBIERZ KARNET</label>
          <select id="demo-plan" v-model="selectedPlan" required>
            <option disabled value="">Wybierz pakiet</option>
            <option value="BASIC">BASIC — 99 zł / miesiąc</option>
            <option value="PRO">PRO — 149 zł / miesiąc</option>
            <option value="ELITE">ELITE — 229 zł / miesiąc</option>
          </select>

          <button type="submit">
            PRZETESTUJ FORMULARZ <span>↗</span>
          </button>

          <p class="form-disclaimer">
            Projekt portfolio Tovexa Studio. Nie wpisuj
            prawdziwych danych osobowych. Żadne dane
            nie są przesyłane na serwer.
          </p>
        </form>

        <div v-else class="success-message" role="status">
          <div class="success-icon">✓</div>
          <h4>DEMONSTRACJA ZAKOŃCZONA</h4>
          <p>
            Tak mógłby wyglądać komunikat po wysłaniu
            formularza. Żadne dane nie zostały wysłane.
          </p>
          <button type="button" @click="submitted = false">
            PRZETESTUJ PONOWNIE
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-section {
  padding: 125px 0;
  background:
    radial-gradient(circle at 10% 60%, #53101040, transparent 45%),
    #0b0b0b;
}

.contact-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 85px;
  align-items: center;
}

.eyebrow {
  color: #ff5555;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
  margin-bottom: 20px;
}

.contact-content .section-title {
  margin: 0 0 30px;
}

.contact-content > p {
  max-width: 480px;
  color: #aaa;
  font-size: 15px;
  line-height: 1.9;
}

.contact-info {
  margin-top: 45px;
  display: grid;
  gap: 30px;
}

.info-item {
  display: flex;
  gap: 20px;
  align-items: flex-start;
}

.info-item > span {
  color: #ff4545;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 27px;
  font-weight: 800;
}

.info-item strong {
  font-size: 13px;
  letter-spacing: 1px;
}

.info-item p {
  margin: 9px 0 0;
  color: #aaa;
  font-size: 13px;
  line-height: 1.7;
}

.contact-form-wrapper {
  padding: 43px;
  border: 1px solid #383838;
  background: #171717;
}

.form-header > span {
  color: #ff5555;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 2px;
}

.form-header h3 {
  margin: 14px 0;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 43px;
  line-height: 1;
}

.form-header p {
  color: #aaa;
  font-size: 13px;
  line-height: 1.8;
}

form {
  display: flex;
  flex-direction: column;
  margin-top: 30px;
}

label {
  margin-bottom: 10px;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1px;
}

input,
select {
  width: 100%;
  min-height: 54px;
  margin-bottom: 23px;
  padding: 0 16px;
  border: 1px solid #444;
  border-radius: 0;
  background: #101010;
  color: white;
  font: inherit;
  font-size: 13px;
  outline: none;
}

input:focus,
select:focus {
  border-color: #ff4545;
}

input::placeholder {
  color: #888;
}

form > button,
.success-message button {
  display: flex;
  justify-content: space-between;
  align-items: center;
  min-height: 58px;
  padding: 0 22px;
  border: 0;
  background: #ed2828;
  color: white;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 1px;
}

form > button:hover,
.success-message button:hover {
  background: #bf2020;
}

.form-disclaimer {
  margin: 18px 0 0;
  color: #aaa;
  font-size: 11px;
  line-height: 1.8;
}

.success-message {
  padding: 45px 0 10px;
  text-align: center;
}

.success-icon {
  display: grid;
  place-items: center;
  width: 65px;
  height: 65px;
  margin: 0 auto 25px;
  background: #1c542d;
  color: white;
  font-size: 35px;
}

.success-message h4 {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 30px;
}

.success-message p {
  color: #aaa;
  font-size: 13px;
  line-height: 1.8;
}

.success-message button {
  margin: 25px auto 0;
}

@media (max-width: 950px) {
  .contact-layout {
    grid-template-columns: 1fr;
    gap: 55px;
  }
}

@media (max-width: 650px) {
  .contact-section {
    padding: 80px 0;
  }

  .contact-content .section-title {
    font-size: 58px;
  }

  .contact-form-wrapper {
    padding: 25px;
  }
}
</style>
