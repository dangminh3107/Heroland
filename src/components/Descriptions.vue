<template>
  <div class="description-contain">
    <div class="grid-contain">
      <div class="text-contain">
        <p v-html="text"></p>
      </div>
      <div class="img-contain">
        <img :src="Artboard35" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
import Artboard35 from "../assets/images/Artboard 35.png";
export default {
  name: "DescriptionsComponent",
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
    };
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
    .text-contain {
      font-size: 1vw;
      line-height: 30px;
    }
    .img-contain {
      display: flex;
      justify-content: center;
      align-items: center;
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
