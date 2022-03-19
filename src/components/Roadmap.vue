<template>
  <div class="roadmap-wrapper">
    <div class="roadmap-contain-img">
      <div class="grid">
        <div :class="['roadmap-title', isActive1 ? 'active' : '']" ref="myRef1">
          <img :src="Artboard75" alt="" />
        </div>
        <img
          :src="Artboard29"
          alt=""
          :class="['map', isActive2 ? 'active' : '']"
          ref="myRef2"
        />
      </div>
    </div>
    <div :class="['backer-title', isActive3 ? 'active' : '']">
      <img :src="Artboard75_1" alt="" ref="myRef3"/>
    </div>
  </div>
</template>

<script>
import Artboard29 from "../assets/images/Artboard 29.png";
import Artboard75 from "../assets/images/Artboard 75.png";
import Artboard75_1 from "../assets/images/Artboard 75_1.png";
export default {
  name: "RoadmapComponent",
  props: ["pos"],
  data() {
    return {
      Artboard29,
      Artboard75_1,
      Artboard75,
      isActive1: false,
      isActive2: false,
      isActive3: false,
    };
  },
  watch: {
    pos: function () {
      let x1 =
        this.$refs.myRef1.getBoundingClientRect().top -
        this.$refs.myRef1.getBoundingClientRect().height -
        this.$refs.myRef1.getBoundingClientRect().height / 2;
      let x2 =
        this.$refs.myRef2.getBoundingClientRect().top -
        this.$refs.myRef2.getBoundingClientRect().height -
        this.$refs.myRef2.getBoundingClientRect().height / 2;
      let x3 =
        this.$refs.myRef3.getBoundingClientRect().top -
        this.$refs.myRef3.getBoundingClientRect().height * 6;
      if (x1 <= 0) this.isActive1 = true;
      else this.isActive1 = false;
      if (x2 <= 0) this.isActive2 = true;
      else this.isActive2 = false;
      if (x3 <= 0) this.isActive3 = true;
      else this.isActive3 = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.roadmap-wrapper {
  background-image: url("../assets/images/Artboard 36.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top center;
  display: flex;
  align-items: center;
  flex-direction: column;
  .roadmap-contain-img {
    margin-top: 260px;
    background-image: url("../assets/images/Artboard 41.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: top center;
    width: 100%;
    display: flex;
    justify-content: center;
    .grid {
      display: flex;
      flex-direction: column;
      align-items: center;
      max-width: 1200px;
      .roadmap-title {
        padding: 64px 0 88px;
        perspective: 1000px;
        transition: all 1.5s ease;
        opacity: 0;
        transform: rotateY(180deg);
        transform-style: preserve-3d;
        backface-visibility: hidden;
        &.active {
          opacity: 1;
          transform: rotateY(0);
        }
        img {
          max-width: 230px;
          object-fit: contain;
          @media screen and (max-width: 300px) {
            max-width: 100%;
          }
        }
      }
      .map {
        width: 100%;
        object-fit: contain;
        perspective: 1000px;
        transition: all 1.5s ease;
        opacity: 0;
        transform: rotateY(-180deg);
        transform-style: preserve-3d;
        backface-visibility: hidden;
        &.active {
          opacity: 1;
          transform: rotateY(0);
        }
      }
    }
  }
  .backer-title {
    margin: 100px 0;
    transform: translateX(150%);
    transition: all 1s ease;
    opacity: 0;
    &.active {
      opacity: 1;
      transform: translateX(0);
    }
    img {
      max-width: 320px;
      object-fit: contain;
      @media screen and (max-width: 400px) {
        max-width: 100%;
      }
    }
  }
}
</style>
