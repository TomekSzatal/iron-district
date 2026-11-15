
<script setup lang="ts">
import { ref } from 'vue'

const activeIndex = ref<number | null>(0)

const questions = [
  {
    question: 'Czy siłownia jest otwarta przez całą dobę?',
    answer:
      'W demonstracyjnej ofercie IRON DISTRICT karnety PRO i ELITE zapewniają dostęp 24/7. Pakiet BASIC obejmuje godziny 6:00–22:00.',
  },
  {
    question: 'Czy mogę trenować bez doświadczenia?',
    answer:
      'Tak. Przykładowa oferta klubu została przygotowana zarówno dla osób początkujących, jak i zaawansowanych.',
  },
  {
    question: 'Czy dostępne są treningi personalne?',
    answer:
      'Tak. Demonstracyjny pakiet ELITE obejmuje dwa treningi personalne miesięcznie.',
  },
  {
    question: 'Czy mogę zmienić karnet?',
    answer:
      'W rzeczywistym klubie zasady zmiany karnetu określałby regulamin. Tutaj pakiety są wyłącznie przykładem projektu strony.',
  },
  {
    question: 'Jak mogę dołączyć do klubu?',
    answer:
      'IRON DISTRICT jest fikcyjną marką stworzoną do portfolio Tovexa Studio. Na tej stronie nie można kupić prawdziwego karnetu.',
  },
]

function toggle(index: number) {
  activeIndex.value = activeIndex.value === index ? null : index
}
</script>

<template>
  <section id="faq" class="faq-section">
    <div class="container faq-layout">
      <div class="faq-intro">
        <div class="eyebrow">MASZ PYTANIA?</div>
        <h2 class="section-title">
          WSZYSTKO<br />
          <span class="accent">JASNE.</span>
        </h2>
        <p>
          Sprawdź odpowiedzi na najczęściej zadawane
          pytania dotyczące przykładowej oferty klubu.
        </p>
        <a href="#kontakt" class="faq-link">
          PRZEJDŹ DO KONTAKTU ↗
        </a>
      </div>

      <div class="faq-list">
        <div
          v-for="(item, index) in questions"
          :key="index"
          class="faq-item"
          :class="{ active: activeIndex === index }"
        >
          <button
            type="button"
            class="faq-question"
            :aria-expanded="activeIndex === index"
            @click="toggle(index)"
          >
            <span>{{ item.question }}</span>
            <span class="faq-icon">
              {{ activeIndex === index ? '−' : '+' }}
            </span>
          </button>

          <div v-if="activeIndex === index" class="faq-answer">
            {{ item.answer }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faq-section {
  padding: 115px 0;
  background: #111;
}

.faq-layout {
  display: grid;
  grid-template-columns: .85fr 1.15fr;
  gap: 90px;
}

.eyebrow {
  color: #ff5555;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 2px;
  margin-bottom: 20px;
}

.faq-intro .section-title {
  margin: 0 0 28px;
}

.faq-intro p {
  color: #aaa;
  font-size: 14px;
  line-height: 1.9;
}

.faq-link {
  display: inline-block;
  margin-top: 25px;
  padding-bottom: 10px;
  border-bottom: 2px solid #ed2828;
  color: white;
  font-size: 12px;
  font-weight: 800;
  letter-spacing: 1px;
}

.faq-item {
  border-bottom: 1px solid #333;
}

.faq-question {
  width: 100%;
  min-height: 86px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  padding: 18px 0;
  border: 0;
  background: transparent;
  color: white;
  text-align: left;
  font-size: 15px;
  font-weight: 700;
}

.faq-icon {
  display: grid;
  place-items: center;
  flex-shrink: 0;
  width: 34px;
  height: 34px;
  border: 1px solid #555;
  color: #ff5555;
  font-size: 24px;
}

.faq-item.active .faq-icon {
  background: #ed2828;
  border-color: #ed2828;
  color: white;
}

.faq-answer {
  padding: 0 45px 25px 0;
  color: #aaa;
  font-size: 14px;
  line-height: 1.9;
}

@media (max-width: 900px) {
  .faq-layout {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}

@media (max-width: 650px) {
  .faq-section {
    padding: 80px 0;
  }

  .faq-intro .section-title {
    font-size: 52px;
  }
}
</style>
