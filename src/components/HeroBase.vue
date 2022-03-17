<template>
  <div class="hero-base">
    <div class="title-wrapper">
      <h1>{{ title }}</h1>
      <span class="cursor"></span>
    </div>
    <div class="content">
      <img :src="Artboard20" alt="" />
    </div>
  </div>
</template>

<script>
import Artboard24 from "../assets/images/Artboard 24.png";
import Artboard20 from "../assets/images/Artboard 20.png";
import Artboard82 from "../assets/images/Artboard 82.png";
export default {
  name: "HeroBaseComponent",
  data() {
    return {
      title: "HEROLAND BASE",
      Artboard24,
      Artboard20,
      Artboard82,
    };
  },
};
</script>

<style lang="scss" scoped>
.hero-base {
  width: 100%;
  margin: 150px 0 50px;
  min-height: 250px;
  background-image: url("../assets/images/Artboard 82.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  .title-wrapper {
    display: flex;
    background-color: var(--main-color);
    padding: 0 1px 15px 0;
    position: absolute;
    top: 0;
    transform: translateY(-90%);
    h1 {
      font-size: 48px;
      line-height: 48px;
      display: inline-block;
      color: var(--black-color);
    }
    .cursor {
      height: 8px;
      width: 25px;
      background: var(--black-color);
      align-self: end;
      animation: blinkCursor 0.8s steps(3) infinite;
      @media screen and (min-width: 848px) and (max-width: 1024px) {
        height: 6px;
      }
      @media screen and (max-width: 848px) {
        height: 4px;
        width: 20px;
      }
      @keyframes blinkCursor {
        0%,
        75% {
          opacity: 1;
        }
        76%,
        100% {
          opacity: 0;
        }
      }
    }
  }
  .content {
    padding: 0 20px;
    max-width: 1200px;
    img {
      width: 100%;
      object-fit: contain;
    }
  }
}
</style>
