<template>
  <div class="hero-base" ref="myRef">
    <div :class="['title-wrapper', isActive ? 'active' : '']">
      <h1>{{ title }}</h1>
      <span class="cursor"></span>
    </div>
    <div :class="['content', isActive ? 'active' : '']">
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
  props: ["pos"],
  data() {
    return {
      title: "HEROLAND BASE",
      Artboard24,
      Artboard20,
      Artboard82,
      isActive: false,
    };
  },
  watch: {
    pos: function (newPos) {
      let x =
        this.$refs.myRef.getBoundingClientRect().top +
        this.$refs.myRef.getBoundingClientRect().height / 2;
      if (newPos > x) this.isActive = true;
      else this.isActive = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.hero-base {
  width: 100%;
  margin: 150px 0 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  .title-wrapper {
    display: flex;
    background-color: var(--main-color);
    padding: 0 1px 15px 0;
    top: 0;
    transition: all 1s ease-in-out;
    transform: translateY(-100%);
    opacity: 0;
    z-index: 2;
    &.active {
      transform: translateY(20%);
      opacity: 1;
    }
    h1 {
      font-size: 48px;
      line-height: 48px;
      display: inline-block;
      color: var(--black-color);
      @media screen and (max-width: 400px) {
        font-size: 11vw;
      }
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
    min-height: 250px;
    width: 100%;
    background-image: url("../assets/images/Artboard 82.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 1.5s ease-in-out;
    opacity: 0;
    transform: translateY(150%);
    &.active {
      opacity: 1;
      transform: translateY(0);
    }
    img {
      max-width: 1200px;
      object-fit: contain;
      @media screen and (max-width: 1200px) {
        max-width: 100%;
      }
    }
  }
}
</style>
