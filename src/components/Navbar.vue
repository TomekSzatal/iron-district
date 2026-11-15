
<script setup lang="ts">
import { ref } from 'vue'

const menuOpen = ref(false)

const links = [
  { label: 'Start', href: '#start' },
  { label: 'O klubie', href: '#o-klubie' },
  { label: 'Strefy', href: '#strefy' },
  { label: 'Trenerzy', href: '#trenerzy' },
  { label: 'Karnety', href: '#karnety' },
]
</script>

<template>
  <header class="navbar">
    <div class="container nav-inner">
      <a href="#start" class="logo" @click="menuOpen = false">
        IRON<span>DISTRICT</span><b>.</b>
      </a>

      <nav :class="{ open: menuOpen }" aria-label="Menu główne">
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          @click="menuOpen = false"
        >
          {{ link.label }}
        </a>

        <a href="#kontakt" class="nav-cta" @click="menuOpen = false">
          DOŁĄCZ TERAZ
        </a>
      </nav>

      <button
        class="menu-toggle"
        type="button"
        :aria-expanded="menuOpen"
        aria-label="Otwórz lub zamknij menu"
        @click="menuOpen = !menuOpen"
      >
        {{ menuOpen ? '✕' : '☰' }}
      </button>
    </div>
  </header>
</template>

<style scoped>
.navbar {
  position: absolute;
  z-index: 100;
  top: 0;
  left: 0;
  width: 100%;
  border-bottom: 1px solid #ffffff24;
  background: #080808a6;
  backdrop-filter: blur(16px);
}

.nav-inner {
  min-height: 86px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
}

.logo {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 29px;
  font-weight: 900;
  letter-spacing: -0.5px;
  white-space: nowrap;
}

.logo span {
  color: #ff3434;
}

.logo b {
  color: #fff;
}

nav {
  display: flex;
  align-items: center;
  gap: 30px;
}

nav > a {
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.6px;
  text-transform: uppercase;
  transition: color 0.2s;
}

nav > a:hover {
  color: #ff3434;
}

nav .nav-cta {
  padding: 14px 19px;
  background: #ed2828;
  color: white;
}

nav .nav-cta:hover {
  background: #c71f1f;
  color: white;
}

.menu-toggle {
  display: none;
  border: 0;
  background: transparent;
  color: white;
  font-size: 27px;
}

@media (max-width: 900px) {
  .menu-toggle {
    display: block;
  }

  nav {
    display: none;
    position: absolute;
    top: 86px;
    left: 0;
    right: 0;
    padding: 25px;
    flex-direction: column;
    align-items: stretch;
    gap: 22px;
    background: #111;
    border-bottom: 1px solid #333;
  }

  nav.open {
    display: flex;
  }

  nav .nav-cta {
    text-align: center;
  }
}
</style>
