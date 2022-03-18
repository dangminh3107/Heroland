<template>
  <div class="hbg-contain">
    <div class="mask">
      <LandOwner />
      <div class="grid-wrapper">
        <div class="defination">
          <div>
            <img :src="Artboard38" alt="" />
          </div>
          <p>{{ text_1 }}</p>
        </div>
        <div class="hbg-help">
          <div>
            <img :src="Artboard97" alt="" />
          </div>
          <p v-html="text_2"></p>
          <div class="btn-wrapper">
            <div v-for="(item, index) in button" :key="index">
              <img :src="item" alt="" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <HBGEcosystem />
  </div>
</template>

<script>
// import Artboard83 from "../assets/images/Artboard 83.png"
import LandOwner from "./LandOwner.vue";
import HBGEcosystem from "./HBGEcosystem.vue"
import Artboard38 from "../assets/images/Artboard 38.png";
import Artboard97 from "../assets/images/Artboard 97.png";
import button1 from "../assets/images/button 1.png";
import button2 from "../assets/images/button 2.png";
import button3 from "../assets/images/button 3.png";
import button4 from "../assets/images/button 4.png";
import button5 from "../assets/images/button 5.png";
export default {
  components: {
    LandOwner, HBGEcosystem
  },
  name: "BlockHBGComponent",
  data() {
    return {
      // eslint-disable-next-line vue/no-parsing-error
      text_1:
        "Hero Book's huge ecosystem needs a factor that links all of them-that's when the HBG Token appears and connects everything.",
      text_2: `Buy Hero Boxes or Land to own your NFT</br>
              Buy, sell, exchange nft in the ecosystem</br>
              Build your own Blockchain Game on the HeroBook system with our support.`,
      Artboard38,
      Artboard97,
      button: [button1, button2, button3, button4, button5],
    };
  },
};
</script>

<style lang="scss" scoped>
.hbg-contain {
  width: 100%;
  background-image: url("../assets/images/Artboard 28.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  .mask {
    width: 100%;
    background-image: url("../assets/images/Artboard 83.png");
    background-repeat: no-repeat;
    background-size: 100% 100%;
    background-position: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    .grid-wrapper {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      overflow: hidden;
      width: 100%;
      top: -80px;
      .defination {
        font-size: 1.4vw;
        max-width: 900px;
        color: var(--white-color);
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-bottom: 100px;
        div {
          margin-bottom: 10px;
          img {
            max-width: 560px;
            object-fit: contain;
          }
          @media screen and (max-width: 572px) {
            width: 100%;
            padding: 0 20px;
            img {
              width: 100%;
              object-fit: contain;
            }
          }
        }
        @media screen and (max-width: 1330px) {
          font-size: 2vw;
          p {
            padding: 0 20px;
          }
        }
        @media screen and (max-width: 970px) {
          font-size: 2.5vw;
        }
        @media screen and (max-width: 640px) {
          font-size: 3vw;
        }
      }
      .hbg-help {
        font-size: 1.4vw;
        color: var(--white-color);
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        width: 1200px;
        @media screen and (max-width: 1200px) {
          width: 100%;
        }
        div {
          margin-bottom: 10px;
          img {
            max-width: 430px;
            object-fit: contain;
          }
          @media screen and (max-width: 560px) {
            width: 100%;
            padding: 0 20px;
            img {
              width: 100%;
              object-fit: contain;
            }
          }
        }
        .btn-wrapper {
          width: 100%;
          margin-top: 50px;
          display: grid;
          grid-template-columns: repeat(auto-fit, 200px);
          justify-content: space-between;
          div {
            cursor: pointer;
            transition: all 0.4s ease-in-out;
            &:hover {
              transform: scale(1.05);
              filter: brightness(1.4);
            }
            img {
              max-width: 180px;
            }
          }
          @media screen and (max-width: 1024px) {
            justify-content: center;
          }
        }
        @media screen and (max-width: 1330px) {
          font-size: 2vw;
          p {
            padding: 0 20px;
          }
        }
        @media screen and (max-width: 970px) {
          font-size: 2.5vw;
        }
        @media screen and (max-width: 640px) {
          font-size: 3vw;
        }
      }
    }
  }
}
</style>
