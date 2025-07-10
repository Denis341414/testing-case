<script setup>
import Header from "./components/Header/ui/Header.vue";
import Main from "./components/Main/ui/Main.vue";
</script>

<template>
  <div class="container">
    <Header />
    <Main />
  </div>
</template>

<style scoped lang="scss">
.container {
  padding: 8px 120px;
  min-height: 100vh;
  width: 100vw;

  @media (max-width: 1024px) {
    padding: 8px 10px;
  }
  @media (max-width: 480px) {
    padding: 32px 10px;
  }
}
</style>
