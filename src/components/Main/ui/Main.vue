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
  <main class="main">
    <video
      class="main-video"
      src="../assets/Видео без названия — сделано в Clipchamp (4).mp4"
      type="video/mp4"
      autoplay
      muted
      loop
    ></video>
    <div class="main-content">
      <div class="block-left">
        <h1 class="title" v-if="widthScreen > 360">
          Просто потому <br />
          что можем
        </h1>
        <div class="subtext" v-if="widthScreen > 500">
          Мы запустили основной цикл в 06:42. Результаты наблюдаются, но не
          зафиксированы. Рекомендуем сохранять спокойствие до следующего
          сигнала.
        </div>
        <button v-if="widthScreen > 500" class="button-side">
          <div class="button-text">Попробовать просто так</div>
          <img
            class="button-image"
            src="../assets/button-png.png"
            alt="button"
          />
        </button>
      </div>
      <div class="block-right">
        <div class="subscribe" v-if="widthScreen > 500">
          Сертификат есть. Но это не точно <br />
          СГР №AM.01.01 .01.003.R.00 o47 4.06.24
        </div>
      </div>
    </div>
  </main>

  <div class="sub-main-container">
    <h1 class="title" v-if="widthScreen < 360">
      Просто потому <br />
      что можем с Collagen
    </h1>
    <div v-if="widthScreen < 500" class="subtext-1">
      Мы запустили основной цикл в 06:42. Результаты наблюдаются, но не
      зафиксированы. Рекомендуем сохранять спокойствие до следующего сигнала.
    </div>
    <button v-if="widthScreen < 500" class="button-side">
      <div class="button-text">Попробовать просто так</div>
      <img class="button-image" src="../assets/button-png.png" alt="button" />
    </button>
    <div class="subscribe" v-if="widthScreen < 500">
      Сертификат есть. Но это не точно СГР №AM.01.01 .01.003.R.00 o47 4.06.24
    </div>
  </div>
</template>

<style scoped lang="scss">
.main {
  position: relative;
  width: 100%;
  height: 50vh;
  z-index: 0;
  font-family: "Tektur", sans-serif;

  @media (max-width: 500px) {
    height: 40vh;
  }
}

.main-video {
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100%;
  height: 560px;
  object-fit: cover;
  border-radius: 24px;

  @media (max-width: 1024px) {
    height: 400px;
  }
  @media (max-width: 640px) {
    height: 360px;
  }
  @media (max-width: 500px) {
    height: 260px;
  }
}
.main-content {
  display: flex;
  justify-content: space-between;
  align-items: end;
  z-index: 2;
  padding: 64px;
  color: #ffffff;

  @media (max-width: 640px) {
    padding: 24px;
  }

  .block-left {
    display: flex;
    flex-direction: column;
    gap: 32px;

    .title {
      font-size: 64px;
      @media (max-width: 1024px) {
        font-size: 32px;
      }
    }
    .subtext {
      width: 21.2em;
      font-size: 21px;
      font-family: "Tilda Sans VF";
      @media (max-width: 1024px) {
        font-size: 18px;
        width: 18em;
      }
    }

    .button-side {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 16px;
      padding: 20px 24px;
      border-radius: 40px;
      background: #1f8b48;
      max-width: max-content;
      cursor: pointer;
      transition: all 0.2s ease-in-out;

      .button-text {
        font-size: 21px;
        font-family: "Tektur", sans-serif;
        font-size: 18px;
        color: #ffffff;

        @media (max-width: 1024px) {
          font-size: 16px;
        }
      }
    }
    .button-side:hover {
      background: #25a757;
      box-shadow: 1px 1px 10px rgb(0, 163, 0);
    }
  }

  .subscribe {
    text-align: right;
    font-family: "Tilda Sans VF";
    font-size: 16px;
    line-height: 2;

    @media (max-width: 640px) {
      font-size: 12px;
    }
  }
}

.sub-main-container {
  display: flex;
  flex-direction: column;
  gap: 24px;

  .title {
    font-size: 32px;
    font-family: "Tektur", sans-serif;
  }

  .subtext-1 {
    font-size: 18px;
    font-family: "Tilda Sans VF";
  }

  .button-side {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 16px;
    padding: 20px 24px;
    border-radius: 40px;
    background: #1f8b48;
    max-width: max-content;
    cursor: pointer;
    transition: all 0.2s ease-in-out;

    @media (max-width: 360px) {
      min-width: 90vw;
    }

    .button-text {
      font-size: 21px;
      font-family: "Tektur", sans-serif;
      font-size: 18px;
      color: #ffffff;

      @media (max-width: 360px) {
        font-size: 12px;
      }
    }
  }
  .button-side:hover {
    background: #25a757;
    box-shadow: 1px 1px 10px rgb(0, 163, 0);
  }

  .subscribe {
    font-size: 12px;
    color: #2e2d2b;

    @media (max-width: 360px) {
      text-align: center;
    }
  }
}
</style>
