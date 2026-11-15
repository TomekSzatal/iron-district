<script setup lang="ts">
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ZonesSection from './components/ZonesSection.vue'
import TrainersSection from './components/TrainersSection.vue'
import PricingSection from './components/PricingSection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import FAQSection from './components/FAQSection.vue'
import ContactSection from './components/ContactSection.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <Navbar />

  <main>
    <HeroSection />
    <AboutSection />
    <ZonesSection />
    <TrainersSection />
    <PricingSection />
    <TestimonialsSection />
    <FAQSection />
    <ContactSection />
  </main>

  <Footer />
</template>
