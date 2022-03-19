<template>
  <div class="electric-base">
    <div :class="['img-contain', isActive1 ? 'active' : '']" ref="myRef1">
      <img :src="Artboard23" alt="" />
    </div>
    <div :class="['text-contain', isActive2 ? 'active' : '']" ref="myRef2">
      <div>
        <img :src="Artboard37" alt="" />
      </div>
      <p v-html="text"></p>
    </div>
  </div>
</template>

<script>
import Artboard23 from "../assets/images/Artboard 23.png";
import Artboard37 from "../assets/images/Artboard 37.png";
export default {
  name: "ElectricBaseComponent",
  props: ["pos"],
  data() {
    return {
      text: `Lorem ipsum dolor sit amet, consectetur
            adipisicing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna 
            aliqua.</br>Lorem ipsum dolor sit amet, consectetur
            adipisicing elit, sed do eiusmod tempor
            incididunt ut labore et dolore magna 
            aliqua.</br>Lorem ipsum dolor sit amet, consectetur
            adipisicing elit, sed do eiusmod tempor
            incididunt ut labore et dolore mag`,
      Artboard23,
      Artboard37,
      isActive1: false,
      isActive2: false,
    };
  },
  watch: {
    pos: function () {
      let x1 =
        this.$refs.myRef1.getBoundingClientRect().top -
        this.$refs.myRef1.getBoundingClientRect().height * 1.5;
      let x2 =
        this.$refs.myRef2.getBoundingClientRect().top -
        this.$refs.myRef2.getBoundingClientRect().height * 1.5;
      if (x1 <= 0) this.isActive1 = true;
      else this.isActive1 = false;
      if (x2 <= 0) this.isActive2 = true;
      else this.isActive2 = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.electric-base {
  max-width: 1200px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 50px;
  justify-content: space-around;
  overflow: hidden;
  .img-contain {
    display: flex;
    align-items: center;
    justify-content: center;
    transform: translateX(-150%);
    transition: all 1.5s ease;
    opacity: 0;
    &.active {
      opacity: 1;
      transform: translateX(0);
    }
    img {
      max-width: 450px;
      object-fit: contain;
      @media screen and (max-width: 500px) {
        max-width: 100%;
      }
    }
  }
  .text-contain {
    padding: 20px 0 5px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    transition: all 1.5s ease;
    opacity: 0;
    transform: translateX(150%);
    &.active {
      opacity: 1;
      transform: translateX(0);
    }
    div {
      img {
        max-width: 370px;
        object-fit: contain;
      }
      @media screen and (max-width: 640px) {
        width: 100%;
        margin-bottom: 20px;
        img {
          width: 100%;
          object-fit: contain;
        }
      }
    }
    p {
      color: var(--white-color);
      font-size: 18px;
      line-height: 23px;
    }
  }
  @media screen and (max-width: 970px) {
    display: flex;
    flex-direction: column;
    justify-content: center;
    .text-contain {
      align-items: center;
      padding: 50px;
      text-align: center;
    }
  }
}
</style>
