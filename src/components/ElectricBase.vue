<template>
  <div class="electric-base">
    <div class="img-contain">
      <img :src="Artboard23" alt="" />
    </div>
    <div class="text-contain">
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
    };
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
  .img-contain {
    display: flex;
    align-items: center;
    justify-content: center;
    img {
      max-width: 450px;
      object-fit: contain;
    }
  }
  .text-contain {
    padding: 20px 0 5px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
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
