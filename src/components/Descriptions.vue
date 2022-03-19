<template>
  <div class="description-contain">
    <div class="grid-contain">
      <div :class="['text-contain',isActive1 ? 'active' : '']" ref="myRef1">
        <p v-html="text"></p>
      </div>
      <div :class="['img-contain', isActive2 ? 'active' : '']" ref="myRef2">
        <img :src="Artboard35" alt=""/>
      </div>
    </div>
  </div>
</template>

<script>
import Artboard35 from "../assets/images/Artboard 35.png";
export default {
  name: "DescriptionsComponent",
  props: ['pos'],
  data() {
    return {
      text: `Heroland is a 1:1 virtual version of Mars divided into
          16,700,000 land plots. However, the player can only own a
          third of the purchased plots and the remaining plots will
          be </br> released in later stages through Punitive Expedition Mode.
          Ownership and exchange of plots in Heroland is completely
          allowed. Then, use NFT Hero to build and exploit buildings
          to </br> develop income when owning land </br> Become a real estate tycoon in the world of HeroLand. Sell
          them or explore the potential hidden under the soil layers?
          The decision is up to you!`,
      Artboard35,
      isActive1: false,
      isActive2: false,
    };
  },
  watch: {
    pos: function (newPos) {
      let x1 = this.$refs.myRef1.getBoundingClientRect().top + this.$refs.myRef1.getBoundingClientRect().height / 2;
      let x2 = this.$refs.myRef2.getBoundingClientRect().top + this.$refs.myRef2.getBoundingClientRect().height / 2;
      if (newPos > x1) this.isActive1=true;
      else this.isActive1=false;
      if (newPos > x2) this.isActive2=true;
      else this.isActive2=false;
    },
  },
};
</script>

<style lang="scss" scoped>
.description-contain {
  background-image: url("../assets/images/Artboard 32.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top center;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 100px 0;
  .grid-contain {
    max-width: 1200px;
    display: grid;
    justify-content: center;
    color: var(--white-color);
    grid-template-columns: 2fr 1fr;
    column-gap: 50px;
    align-items: center;
    overflow: hidden;
    .text-contain {
      font-size: 1vw;
      line-height: 30px;
      transition: all 1.5s ease;
      transform: translateX(-100%);
      opacity: 0;
      &.active {
        transform: translateX(0);
        opacity: 1;
      }
    }
    .img-contain {
      display: flex;
      justify-content: center;
      align-items: center;
      transition: all 1.5s ease;
      transform: translateX(100%);
      opacity: 0;
      &.active {
        transform: translateX(0);
        opacity: 1;
      }
      img {
        width: 28vw;
        object-fit: contain;
      }
    }
    @media screen and (max-width: 1240px) {
      grid-template-columns: unset;
      max-width: 800px;
      .text-contain {
        font-size: 16px;
        margin-bottom: 50px;
        @media screen and (max-width: 848px) {
          padding: 0 20px;
          font-size: 14px;
        }
      }
      .img-contain {
        img {
          width: 40vw;
          @media screen and (max-width: 848px) {
            width: 70vw;
          }
        }
      }
    }
  }
}
</style>
