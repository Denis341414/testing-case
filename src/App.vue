<script setup>
import Contacts from "./components/Contacts/ui/Contacts.vue";
import Form from "./components/Forn/ui/Form.vue";
import Header from "./components/Header/ui/Header.vue";
import Main from "./components/Main/ui/Main.vue";
import Slider from "./components/Slider/ui/Slider.vue";
</script>

<template>
  <div class="container">
    <Header />
    <Main />
    <Slider />
    <Form />
    <Contacts />
  </div>
</template>

<style scoped lang="scss">
.container {
  display: flex;
  flex-direction: column;
  gap: 3em;
  padding: 8px 120px;
  min-height: 100vh;
  max-width: 100vw;

  @media (max-width: 1024px) {
    padding: 8px 10px;
    gap: 1em;
  }
  @media (max-width: 480px) {
    padding: 32px 10px;
    gap: 1em;
  }
}
</style>
