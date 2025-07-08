<script setup></script>

<template>
  <header class="header">
    <div class="logo">
      <img src="../assets/header-logo.svg" alt="logo" />
    </div>
    <div class="line-nav">
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
  width: 100%;
  background: #ffffff;
  border-radius: 24px;
}

.line-nav {
  display: flex;
  gap: 32px;

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
</style>
