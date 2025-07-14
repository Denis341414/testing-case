<script setup></script>

<template>
  <div class="form">
    <div class="block-text">
      <h2 class="title">Если вы тоже решили «а почему бы и нет»</h2>
      <div class="info">
        <li class="item-info item">
          <img
            class="img-item"
            src="../assets/info-image.png"
            alt="logo-li"
          />Можно заказать много
        </li>
        <li class="item-info item">
          <img
            class="img-item"
            src="../assets/info-image.png"
            alt="logo-li"
          />Доступ возможен через северный интерфейс
        </li>
        <li class="item-info item">
          <img
            class="img-item"
            src="../assets/info-image.png"
            alt="logo-li"
          />Можно просто поболтать
        </li>
      </div>
    </div>
    <div class="block-forms">
      <div class="form-inputs">
        <input type="text" class="name input" placeholder="Имя" />
        <input type="text" class="phone input" placeholder="Телефон" />
      </div>
      <div class="form-checkbox">
        <input class="checkbox" type="checkbox" name="checkbox" id="1" />
        <label class="label" for="1"
          >Согласен(-на) на обработку чего угодно — лишь бы форма
          работала</label
        >
      </div>
      <div class="button-tosend">
        Отправить
        <img src="../assets/to-send-img.png" alt="to-send" />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.form {
  width: 100%;
  height: 350px;
  background: #1f8b48;
  border-radius: 24px;
  padding: 64px;
  display: flex;
  justify-content: start;

  @media (max-width: 650px) {
    gap: 1em;
    flex-direction: column;
    height: max-content;
    padding: 24px;
  }

  .block-text {
    .title {
      font-size: 40px;
      font-family: "Tektur", sans-serif;
      color: #fff;
      @media (max-width: 1600px) {
        font-size: 28px;
      }
    }
    .info {
      display: flex;
      flex-direction: column;
      gap: 16px;
      font-size: 21px;
      .item {
        display: flex;
        list-style-type: none;
        vertical-align: middle;
        gap: 0.5em;
        color: #fff;
        font-family: "Tilda Sans VF";
        .img-item {
          width: 24px;
          height: 24px;
        }

        @media (max-width: 1200px) {
          font-size: 18px;
        }
      }
    }
  }

  .block-forms {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 16px;
    min-width: 50%;

    .form-inputs {
      display: flex;
      flex-direction: column;
      gap: 16px;
      width: 100%;

      @media (max-width: 650px) {
        gap: 0.5em;
        flex-direction: row;
      }
      @media (max-width: 340px) {
        flex-direction: column;
      }

      .input {
        height: 40px;
        width: 100%;

        border-radius: 40px;
        padding: 8px 24px;
        font-size: 16px;
        font-family: "Tilda Sans VF";
      }
    }

    .form-checkbox {
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 12px;

      .checkbox {
        margin-right: 8px;
      }
      .checkbox {
        appearance: none;
        width: 24px;
        height: 24px;
        background-image: url(../assets/checkbox-off.png);
        background-size: cover;
        background-repeat: no-repeat;
      }
      .checkbox:checked {
        background-image: url(../assets/checkbox-on.png);
      }
      .label {
        color: #fff;
        font-family: "Tilda Sans VF";
      }
    }
  }

  .button-tosend {
    display: flex;
    gap: 4px;
    border-radius: 40px;
    background: #fff;
    padding: 16px 24px;
    font-family: "Tektur", sans-serif;
    transition: all 0.2s ease;
  }
  .button-tosend:hover {
    cursor: pointer;
    background-color: #2dc768;
    box-shadow: 0 0 10px #2dc768;
  }
}
</style>
