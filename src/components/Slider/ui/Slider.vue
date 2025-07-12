<script setup>
import Image1 from "../assets/image-slider-1.jpg";
import Image2 from "../assets/image-slider-2.jpg";
import Image3 from "../assets/image-slider-3.jpg";
import Image4 from "../assets/image-slider-4.jpg";

import { onMounted, reactive, ref } from "vue";

const informationSliders = reactive([
  {
    title: "Немного упругости",
    text: "Чуть-чуть сияния, и ощущение, что вы о себе позаботились",
    image: Image1,
    active: true,
    id: 0,
  },
  {
    title: "Title2",
    text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quidem!",
    image: Image2,
    active: false,
    id: 1,
  },
  {
    title: "Title3",
    text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quidem!",
    image: Image3,
    active: false,
    id: 2,
  },
  {
    title: "Title3",
    text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quidem!",
    image: Image4,
    active: false,
    id: 3,
  },
  {
    title: "Title3",
    text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quidem!",
    image: Image2,
    active: false,
    id: 4,
  },
]);

const currentSlide = ref(0);

const widthScreen = ref(window.screen.width);
const widthSlide = ref(0);

const handleResize = () => {
  widthScreen.value = window.screen.width;
};

const activeSlide = (currentSlide) => {
  for (let i = 0; i < informationSliders.length; i++) {
    if (currentSlide === i) {
      informationSliders[i].active = true;
    } else {
      informationSliders[i].active = false;
    }
  }
};

const clickSlide = (el) => {
  if (widthScreen.value > 700) {
    currentSlide.value = el.id;
    activeSlide(currentSlide.value);
  }
};

const nextSlide = () => {
  currentSlide.value++;
  console.log(currentSlide.value);
  activeSlide(currentSlide.value);
  if (currentSlide.value > 4) {
    currentSlide.value = 0;
    activeSlide(currentSlide.value);
  }
};

const previewSlide = () => {
  if (currentSlide.value > 0) {
    currentSlide.value--;
    console.log(currentSlide.value);
    activeSlide(currentSlide.value);
  } else if (currentSlide.value === 0) {
    console.log(currentSlide.value);
    currentSlide.value = 4;
    activeSlide(currentSlide.value);
  }
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});
</script>

<template>
  <div class="slider-header" v-show="widthScreen < 700">
    Это — не совсем то, что вы думаете
  </div>
  <div class="slider">
    <div class="main-slide" v-show="widthScreen > 700">
      <div class="main-title">Это — не совсем то, что вы думаете</div>

      <div class="buttons-control">
        <button class="button-slide preview" @click="previewSlide()"></button>
        <button class="button-slide next" @click="nextSlide($event)"></button>
      </div>
    </div>
    <div class="container-slides">
      <div
        class="slide"
        v-for="(el, index) in informationSliders"
        :key="index"
        @click="clickSlide(el)"
        :class="{ active: (el.active === true) | (widthScreen < 700) }"
        :style="{
          backgroundImage: `url(${el.image})`,
          backgroundSize: 'cover',
          backgroundPosition: 'center',
          marginLeft: `${-currentSlide * 20}em`,
        }"
      >
        <div class="title" v-show="el.active | (widthScreen < 700)">
          {{ el.title }}
        </div>
        <div class="subtext" v-show="el.active | (widthScreen < 700)">
          {{ el.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.slider-header {
  font-size: 28px;
  font-family: "Tektur", sans-serif;
}

.slider {
  display: flex;
  gap: 1.2em;
  overflow: hidden;

  @media (max-width: 700px) {
    overflow-x: scroll;
    scrollbar-width: none;
  }

  .container-slides {
    min-width: 100vw;
    overflow: hidden;
    display: flex;
    justify-content: space-around;
    gap: 1.2em;

    @media (max-width: 700px) {
      min-width: max-content;
    }
  }

  .main-slide {
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    min-width: 21em;
    height: 28em;

    @media (max-width: 1024px) {
      min-width: 15em;
      height: 18em;
    }

    .main-title {
      font-size: 40px;
      font-family: "Tektur", sans-serif;

      @media (max-width: 1024px) {
        font-size: 24px;
      }
    }

    .buttons-control {
      .button-slide {
        width: 4em;
        height: 2em;
        border-radius: 24px;
        border: none;
        transition: all 0.3s ease-in-out;
      }

      .button-slide:hover {
        cursor: pointer;
        box-shadow: 0 5px 10px #00ff40;
      }
      .button-slide:active {
        transform: scale(0.9);
      }

      .next {
        background: url("../assets/button-next.png") no-repeat;
      }
      .preview {
        background: url("../assets/button-preview.png") no-repeat;
      }
    }
  }

  .slide {
    width: 21em;
    height: 28em;
    background-color: #8f8f8f;
    padding: 3em;
    border-radius: 24px;
    transition: all 0.3s ease-in-out;
    color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: end;

    @media (max-width: 1024px) {
      width: 15em;
      height: 18em;
      padding: 1em;
    }
    @media (max-width: 700px) {
    }

    .title {
      font-family: "Tektur", sans-serif;
      font-size: 24px;
      margin-bottom: 8px;
    }
    .subtext {
      font-size: 16px;
    }
  }
  .active {
    width: 25em;
    box-shadow: 0px -100px 200px #1f8b48 inset;

    @media (max-width: 1024px) {
      width: 15em;
    }
  }
}
</style>
