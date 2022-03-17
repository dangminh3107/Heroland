<template>
  <div class="landowner">
    <div class="title">
      <h1>{{ title }}</h1>
      <span class="cursor"></span>
    </div>
    <div class="image">
      <img :src="Artboard25" alt="" />
      <div class="content">
        <div class="content-wrapper">
          <div class="content-img">
            <img :src="Artboard27" alt="" />
          </div>
          <div class="content-text">
            <p>{{ text }}</p>
          </div>
        </div>
        <div class="dots">
          <img :src="Artboard77" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Artboard25 from "../assets/images/Artboard 25.png";
import Artboard27 from "../assets/images/Artboard 27.png";
import Artboard77 from "../assets/images/Artboard 77.png";
export default {
  name: "LandOwnerComponent",
  data() {
    return {
      title: "LANDOWNER BENEFITS",
      text: "Sustainable and reputable ecosystem with Herobook and Herocard",
      Artboard25,
      Artboard27,
      Artboard77,
    };
  },
};
</script>

<style lang="scss" scoped>
.landowner {
  position: relative;
  top: -200px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .title {
    margin-bottom: 80px;
    display: flex;
    background-color: var(--main-color);
    padding: 0 1px 15px 0;
    top: 0;
    h1 {
      font-size: 48px;
      line-height: 48px;
      display: inline-block;
      color: var(--black-color);
      @media screen and (max-width: 640px) {
        font-size: 8vw;
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
  .image {
    display: flex;
    position: relative;
    img {
      max-width: 900px;
      object-fit: contain;
      @media screen and (max-width: 970px) {
        max-width: 90vw;
      }
    }
    .content {
      position: absolute;
      top: 0;
      right: 0;
      left: 0;
      bottom: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-around;
      padding: 30px 80px 0;
      @media screen and (max-width: 640px) {
        padding: 20px 50px 0;
      }
      .content-wrapper {
        display: grid;
        grid-template-columns: 1fr 2fr;
        column-gap: 50px;
        .content-img {
          img {
            max-width: 200px;
            object-fit: contain;
            @media screen and (max-width: 970px) {
              max-width: 24vw;
            }
          }
        }
        .content-text {
          padding-top: 20px;
          font-size: 1.5vw;
          color: var(--white-color);
          @media screen and (max-width: 1330px) {
            font-size: 2vw;
          }
          @media screen and (max-width: 970px) {
            font-size: 2.5vw;
          }
          @media screen and (max-width: 640px) {
            font-size: 3vw;
          }
        }
      }
      .dots {
        img {
          max-width: 290px;
          object-fit: contain;
        }
        @media screen and (max-width: 970px) {
          padding: 10px 0;
          img {
            max-width: 30vw;
          }
        }
      }
    }
  }
}
</style>
