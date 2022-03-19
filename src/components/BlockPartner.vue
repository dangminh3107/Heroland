<template>
  <div class="partner-wrapper">
    <div class="backer" ref="myRef1">
      <div
        v-for="(item, index) in imagesTop"
        :key="index"
        :class="[isActive1 ? 'active' : '']"
      >
        <img :src="item" alt="" />
      </div>
    </div>
    <div class="partner">
      <div :class="['title', isActive2 ? 'active' : '']" ref="myRef2">
        <img :src="Artboard50" alt="" />
      </div>
      <div class="image-contain" ref="myRef3">
        <div
          v-for="(item, index) in imagesBottom"
          :key="index"
          :class="[isActive3 ? 'active' : '']"
        >
          <img :src="item" alt="" />
        </div>
      </div>
    </div>
    <div class="start">
      <div :class="['title', isActive4 ? 'active' : '']" ref="myRef4">
        <img :src="Artboard58" alt="" />
      </div>
      <div :class="['button', isActive5 ? 'active' : '']" ref="myRef5">
        <img :src="Artboard59" alt="" />
      </div>
    </div>
    <div class="social">
      <div class="social-grid">
        <div :class="['contact', isActive6 ? 'active' : '']" ref="myRef6">
          <div class="title">
            <div>
              <h3>GET IN TOUCH</h3>
            </div>
            <div>
              <h2>JOIN OUR COMMUNITY</h2>
            </div>
          </div>
          <div class="socials-contain">
            <div v-for="(item, index) in socials" :key="index">
              <img :src="item.image" alt="" />
              <span>{{ item.platform }}</span>
            </div>
          </div>
          <div class="email">
            <span>Contact us: Support@herobook.io</span>
          </div>
        </div>
        <div :class="['image', isActive6 ? 'active' : '']" ref="myRef7">
          <img :src="Artboard73" alt="" />
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Artboard46 from "../assets/images/Artboard 46.png";
import Artboard47 from "../assets/images/Artboard 47.png";
import Artboard48 from "../assets/images/Artboard 48.png";
import Artboard49 from "../assets/images/Artboard 49.png";
import Artboard51 from "../assets/images/Artboard 51.png";
import Artboard53 from "../assets/images/Artboard 53.png";
import Artboard53_1 from "../assets/images/Artboard 53_1.png";
import Artboard54 from "../assets/images/Artboard 54.png";
import Artboard55 from "../assets/images/Artboard 55.png";
import Artboard56 from "../assets/images/Artboard 56.png";
import Artboard50 from "../assets/images/Artboard 50.png";
import Artboard58 from "../assets/images/Artboard 58.png";
import Artboard59 from "../assets/images/Artboard 59.png";
import Artboard66 from "../assets/images/Artboard 66.png";
import Artboard66_1 from "../assets/images/Artboard 66_1.png";
import Artboard67 from "../assets/images/Artboard 67.png";
import Artboard68 from "../assets/images/Artboard 68.png";
import Artboard69 from "../assets/images/Artboard 69.png";
import Artboard73 from "../assets/images/Artboard 73.png";
import Footer from "./Footer.vue";
export default {
  name: "BlockPartnerComponent",
  props: ["pos"],
  components: {
    Footer,
  },
  data() {
    return {
      imagesTop: [Artboard46, Artboard47, Artboard48, Artboard49],
      imagesBottom: [
        Artboard46,
        Artboard47,
        Artboard48,
        Artboard49,
        Artboard51,
        Artboard53,
        Artboard53_1,
        Artboard54,
        Artboard55,
        Artboard56,
      ],
      socials: [
        {
          image: Artboard66,
          platform: "twitter",
        },
        {
          image: Artboard66_1,
          platform: "facebook",
        },
        {
          image: Artboard67,
          platform: "telegram",
        },
        {
          image: Artboard68,
          platform: "email",
        },
        {
          image: Artboard69,
          platform: "website",
        },
      ],
      Artboard50,
      Artboard58,
      Artboard59,
      Artboard73,
      isActive1: false,
      isActive2: false,
      isActive3: false,
      isActive4: false,
      isActive5: false,
      isActive6: false,
      isActive7: false,
    };
  },
  watch: {
    pos: function () {
      let x1 =
        this.$refs.myRef1.getBoundingClientRect().top -
        this.$refs.myRef1.getBoundingClientRect().height -
        this.$refs.myRef1.getBoundingClientRect().height * 4;
      let x2 =
        this.$refs.myRef2.getBoundingClientRect().top -
        this.$refs.myRef2.getBoundingClientRect().height -
        this.$refs.myRef2.getBoundingClientRect().height * 4;
      let x3 =
        this.$refs.myRef3.getBoundingClientRect().top -
        this.$refs.myRef3.getBoundingClientRect().height * 2;
      let x4 =
        this.$refs.myRef4.getBoundingClientRect().top -
        this.$refs.myRef4.getBoundingClientRect().height * 5;
      let x5 =
        this.$refs.myRef5.getBoundingClientRect().top -
        this.$refs.myRef5.getBoundingClientRect().height * 7.5;
      let x6 =
        this.$refs.myRef6.getBoundingClientRect().top -
        this.$refs.myRef6.getBoundingClientRect().height -
        this.$refs.myRef6.getBoundingClientRect().height / 2;
      let x7 =
        this.$refs.myRef7.getBoundingClientRect().top -
        this.$refs.myRef7.getBoundingClientRect().height -
        this.$refs.myRef7.getBoundingClientRect().height / 2;
      if (x1 <= 0) this.isActive1 = true;
      else this.isActive1 = false;
      if (x2 <= 0) this.isActive2 = true;
      else this.isActive2 = false;
      if (x3 <= 0) this.isActive3 = true;
      else this.isActive3 = false;
      if (x4 <= 0) this.isActive4 = true;
      else this.isActive4 = false;
      if (x5 <= 0) this.isActive5 = true;
      else this.isActive5 = false;
      if (x6 <= 0) this.isActive6 = true;
      else this.isActive6 = false;
      if (x7 <= 0) this.isActive7 = true;
      else this.isActive7 = false;
    },
  },
};
</script>

<style lang="scss">
.partner-wrapper {
  background-image: url("../assets/images/Artboard 84.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top center;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
  .backer {
    width: 900px;
    display: flex;
    justify-content: space-between;
    @media screen and (max-width: 912px) {
      display: grid;
      grid-template-columns: repeat(auto-fit, 190px);
      grid-gap: 40px;
      width: 100%;
      justify-content: center;
    }
    div {
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
        max-width: 190px;
      }
    }
  }
  .partner {
    width: 1200px;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 200px 0 120px;
    @media screen and (max-width: 1200px) {
      width: 100%;
    }
    .title {
      margin-bottom: 70px;
      transform: translateX(-150%);
      transition: all 1s ease;
      opacity: 0;
      &.active {
        opacity: 1;
        transform: translateX(0);
      }
      img {
        max-width: 380px;
        object-fit: contain;
        @media screen and (max-width: 400px) {
          max-width: 100%;
        }
      }
    }
    .image-contain {
      display: grid;
      grid-template-columns: repeat(5, 190px);
      grid-gap: 46px;
      @media screen and (max-width: 1150px) {
        width: 100%;
        grid-template-columns: repeat(auto-fit, 190px);
        justify-content: center;
      }
      div {
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
        img {
          max-width: 190px;
        }
      }
    }
  }
  .start {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 120px 0 50px;
    background-image: url("../assets/images/Artboard 72.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
    .title {
      margin-bottom: 100px;
      transition: all 1.5s ease;
      transform: translateY(-150%);
      opacity: 0;
      &.active {
        opacity: 1;
        transform: translateY(0);
      }
      img {
        max-width: 760px;
        object-fit: contain;
        @media screen and (max-width: 768px) {
          max-width: 90vw;
        }
      }
    }
    .button {
      cursor: pointer;
      transition: all 1.5s ease;
      transform: translateY(150%);
      opacity: 0;
      &.active {
        opacity: 1;
        transform: translateY(0);
      }
      img {
        max-width: 260px;
        object-fit: contain;
      }
      &:hover {
        filter: brightness(1.5);
      }
    }
  }
  .social {
    background-image: url("../assets/images/Artboard 71.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
    width: 100%;
    padding: 80px 0 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 2px 0 8px;
    .social-grid {
      display: grid;
      max-width: 1200px;
      grid-template-columns: 1fr 1fr;
      column-gap: 50px;
      @media screen and (max-width: 1200px) {
        width: 100%;
        grid-template-columns: 1fr;
        justify-content: center;
        align-items: center;
      }
      .contact {
        color: var(--white-color);
        transition: all 1s ease;
        transform: translateX(-150%);
        opacity: 0;
        &.active {
          opacity: 1;
          transform: translateX(0);
        }
        @media screen and (max-width: 1200px) {
          display: flex;
          flex-direction: column;
          align-items: center;
          text-align: center;
        }
        .title {
          display: inline-flex;
          flex-direction: column;
          div {
            h2 {
              font-size: 35px;
              line-height: 35px;
              display: inline-block;
              background: var(--black-color);
            }
          }
          div {
            margin-top: 5px;
            h3 {
              font-size: 25px;
              font-weight: lighter;
              line-height: 25px;
              display: inline-block;
              background: var(--black-color);
            }
          }
        }
        .socials-contain {
          display: flex;
          align-items: center;
          margin: 40px 0 30px;
          div {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-right: 30px;
            img {
              width: 45px;
              height: 45px;
              object-fit: contain;
            }
            span {
              color: var(--black-color);
              font-size: 15px;
            }
          }
          @media screen and (max-width: 500px) {
            width: 100%;
            justify-content: space-around;
            div {
              margin-right: 0;
            }
          }
        }
        .email {
          font-size: 18px;
          color: var(--black-color);
        }
      }
      .image {
        transition: all 1s ease;
        transform: translateX(150%);
        opacity: 0;
        &.active {
          opacity: 1;
          transform: translateX(0);
        }
        @media screen and (max-width: 1200px) {
          display: flex;
          flex-direction: column;
          align-items: center;
          text-align: center;
          padding-top: 40px;
        }
        img {
          max-width: 530px;
          object-fit: contain;
          @media screen and (max-width: 564px) {
            max-width: 90vw;
          }
        }
      }
    }
  }
}
</style>
