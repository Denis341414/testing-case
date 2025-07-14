<script setup></script>

<template>
  <div class="contacts">
    <div class="block-left">
      <h2 class="title">Контакты</h2>
      <div class="container-info">
        <div class="point item">
          <img src="../assets/point.png" alt="point" />
          Офис, где делают странные, но симпатичные вещи
        </div>
        <div class="time-work item">
          <img src="../assets/time.png" alt="timework" />
          Пн-Пт с 10:00 до 20:00
        </div>
        <div class="number-phone">
          <div class="phone-item1 item">
            <img src="../assets/phone.png" alt="phone" />
            8 (800) 444 44 44
          </div>
          <div class="phone-item2 item">
            <img src="../assets/phone.png" alt="phone" />
            8 (800) 888 88 88
          </div>
        </div>
        <div class="email item">
          <img src="../assets/email.png" alt="email" />
          example@mail.ru
        </div>
      </div>
      <button class="button-side">
        <div class="button-text">Связться</div>
        <img class="button-image" src="../assets/btn-side.png" alt="button" />
      </button>
    </div>

    <div class="block-right">
      <img class="map" src="../assets/map.png" alt="map" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.contacts {
  display: flex;
  gap: 8px;
  width: 100%;
  height: 60vh;
  @media (max-width: 650px) {
    flex-direction: column;
  }

  .block-left {
    display: flex;
    flex-direction: column;
    gap: 32px;
    background-color: #fff;
    padding: 64px;
    border-radius: 24px;
    width: 50%;
    font-size: 21px;
    min-height: max-content;

    @media (max-width: 1024px) {
      padding: 48px;
    }

    @media (max-width: 650px) {
      padding: 24px;
      width: 100%;
      height: 45vh;
      gap: 24px;
    }

    .title {
      font-size: 40px;
      font-family: "Tektur", sans-serif;
      @media (max-width: 1024px) {
        font-size: 28px;
      }
    }

    .container-info {
      display: flex;
      flex-direction: column;
      gap: 16px;

      img {
        width: 24px;
        height: 24px;
      }

      .item {
        display: flex;
        gap: 2.5px;
        font-family: "Tilda Sans VF";
        @media (max-width: 1024px) {
          font-size: 18px;
        }
      }

      .number-phone {
        display: flex;
        gap: 32px;

        @media (max-width: 360px) {
          flex-direction: column;
        }
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

      @media (max-width: 400px) {
        width: 100%;
      }

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

  .block-right {
    width: 50%;
    @media (max-width: 650px) {
      width: 100%;
    }

    .map {
      width: 100%;
      height: 60vh;
      @media (max-width: 650px) {
        height: 30vh;
      }
    }
  }
}
</style>
