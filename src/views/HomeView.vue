<script setup>
import Footer from '@/components/Footer.vue';
import AboutView from './AboutView.vue';
import DropdownComponent from '@/components/dropdown/DropdownComponent.vue';

function onSelect(item) {
  console.log("Chọn:", item);
}
</script>

<template>
  <DropdownComponent id="gender-dropdown" :arrays="[
    { text: 'Ông', value: 'mr' },
    { text: 'Bà', value: 'mrs' }
  ]" @select="onSelect">
    Chọn xưng hô
  </DropdownComponent>
  <AboutView />
  <Footer />
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
