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
  <header class="header">
    <div class="logo">
      <img src="../assets/header-logo.svg" alt="logo" />
    </div>
    <button v-if="widthScreen < 850" class="button-drawer">
      <img src="../assets/button-img.png" alt="img button" />
    </button>
    <div v-if="widthScreen > 850" class="line-nav">
      <li class="nav-item">О системе</li>
      <li class="nav-item">Архитектура</li>
      <li class="nav-item">Мнения</li>
      <li class="nav-item">Попробовать</li>
      <li class="nav-item">Для своих</li>
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 24px;
  height: 68px;
  margin-bottom: 8px;
  width: 100%;
  background: #ffffff;
  border-radius: 24px;

  @media (max-width: 1024px) {
  }
}

.line-nav {
  display: flex;
  gap: 32px;

  @media (max-width: 1024px) {
    gap: 24px;
  }

  .nav-item {
    list-style-type: none;
    font-family: "Tilda Sans VF";
    padding: 8px 16px;
    transition: all 0.3s ease-in-out;
    cursor: pointer;
  }
  .nav-item:hover {
    background: #1f8b48;
    border-radius: 40px;
    color: #ffffff;
  }
}

.button-drawer {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  background: #1f8b48;
  border-radius: 36px;
}
</style>
