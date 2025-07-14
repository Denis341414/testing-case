<script setup>
import { onMounted, ref } from "vue";

const widthScreen = ref(window.screen.width);

const handleResize = () => {
  widthScreen.value = window.screen.width;
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});
</script>

<template>
  <div class="footer">
    <div v-if="widthScreen < 650" class="logo">
      <img src="../assets/Logo.png" alt="logo" />
    </div>
    <div class="container-nav">
      <p class="item-nav">О системе</p>
      <p class="item-nav">Состав</p>
      <p class="item-nav">Архитектура</p>
      <p class="item-nav">Отзывы</p>
      <p class="item-nav">Для своих</p>
    </div>
    <div class="container-info">
      <div class="cont-text">
        <p class="item-info">Коллаген © 2025</p>
        <p class="item-info">Политика обработки чего-то личного</p>
      </div>
      <div v-if="widthScreen > 650" class="logo">
        <img src="../assets/Logo.png" alt="logo" />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.footer {
  display: flex;
  justify-content: space-between;
  margin-bottom: 2em;
  height: 128px;

  @media (max-width: 650px) {
    flex-direction: column;
    gap: 3em;
  }

  .container-nav {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px 32px;
    font-size: 16px;
    font-family: "Tilda Sans VF";

    @media (max-width: 650px) {
      padding-bottom: 3em;
      border-bottom: 2px solid #2e2d2b;
    }
    @media (max-width: 350px) {
      grid-template-rows: repeat(5, 1fr);
      grid-template-columns: 1fr;
    }
  }

  .container-info {
    font-family: "Tilda Sans VF";
    font-size: 16px;
    display: flex;
    gap: 32px;

    .cont-text {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
  }
}
</style>
