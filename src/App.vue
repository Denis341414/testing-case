<script setup>
import Header from "./components/Header/ui/Header.vue";
</script>

<template>
  <div class="container">
    <Header />
  </div>
</template>

<style scoped lang="scss">
.container {
  padding: 8px 120px;
  background-color: yellow;
  height: 100vh;
  width: 100vw;

  @media (max-width: 1024px) {
    padding: 8px 10px;
  }
  @media (max-width: 480px) {
    padding: 32px 10px;
  }
}
</style>
