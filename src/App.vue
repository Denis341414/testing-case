<script setup>
import Header from "./components/Header/ui/Header.vue";
import Main from "./components/Main/ui/Main.vue";
import Slider from "./components/Slider/ui/Slider.vue";
</script>

<template>
  <div class="container">
    <Header />
    <Main />
    <Slider />
  </div>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
  gap: 1em;
  padding: 8px 120px;
  min-height: 100vh;
  max-width: 100vw;

  @media (max-width: 1024px) {
    padding: 8px 10px;
  }
  @media (max-width: 480px) {
    padding: 32px 10px;
  }
}
</style>
