<template>
  <div class="home-banner">
    <div class="home-content">
      <div class="image-contain">
        <img :src="Artboard9" alt="" />
      </div>
      <div class="text-contain">
        <div class="text-item one">
          <span>BUILD YOUR OWN WORLD</span>
          <div class="cursor"></div>
        </div>
        <div class="text-item two">
          <img :src="Artboard59" alt="" />
          <img :src="Artboard59" alt="" />
        </div>
        <div class="text-item three">
          <button>TRAILER</button>
        </div>
      </div>
    </div>
    <div class="img-footer">
      <img :src="Artboard35_1" alt="" />
    </div>
  </div>
</template>

<script>
import Artboard9 from "../assets/images/Artboard 9.png";
import Artboard59 from "../assets/images/Artboard 59.png";
import Artboard35_1 from "../assets/images/Artboard 35_1.png";
export default {
  name: "HomeComponent",
  data() {
    return {
      Artboard9,
      Artboard59,
      Artboard35_1,
    };
  },
};
</script>

<style lang="scss" scoped>
.home-banner {
  position: relative;
  width: 100%;
  background-image: url("../assets/images/Artboard 2.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  .home-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 150px;
    .image-contain {
      transition: all 0.5s linear;
      img {
        max-width: 350px;
        object-fit: contain;
        animation: appear 4s ease-in-out forwards,
          floating 3s ease-in-out infinite;
      }

      @keyframes appear {
        0% {
          opacity: 0;
        }
        100% {
          opacity: 1;
        }
      }

      @keyframes floating {
        0%,
        100% {
          transform: translateY(-5px);
        }
        50% {
          transform: translateY(5px);
        }
      }
    }
    .text-contain {
      display: flex;
      flex-direction: column;
      align-items: center;
      .text-item {
        display: flex;
        &.one {
          padding: 5px 25px 10px 10px;
          border: 1px solid var(--dark-red);
          background: rgba(15, 7, 9, 0.4);
          span {
            font-size: 3.25vw;
            line-height: 3.25vw;
            color: var(--main-color);
            font-weight: bold;
            position: relative;
            overflow: hidden;
            white-space: nowrap;
            /* animation: typing-1 8s steps(20) infinite; */
            text-shadow: 0 0 4px var(--main-color);
            cursor: text;
            @media screen and (min-width: 848px) and (max-width: 1024px) {
              font-size: 4.5vw;
              line-height: 4.5vw;
              /* animation: typing-2 8s steps(20) infinite; */
            }
            @media screen and (max-width: 848px) {
              font-size: 5.5vw;
              line-height: 5.5vw;
              /* animation: typing-3 8s steps(20) infinite; */
            }
            @keyframes typing-1 {
              0%,
              90%,
              100% {
                width: 0;
              }
              30%,
              60% {
                width: 39.8vw;
              }
            }
            @keyframes typing-2 {
              0%,
              90%,
              100% {
                width: 0;
              }
              30%,
              60% {
                width: 55vw;
              }
            }
            @keyframes typing-3 {
              0%,
              90%,
              100% {
                width: 0;
              }
              30%,
              60% {
                width: 67.5vw;
              }
            }
          }
          .cursor {
            height: 8px;
            width: 25px;
            background: var(--main-color);
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
        &.two {
          min-width: 38vw;
          display: flex;
          justify-content: space-between;
          padding: 30px 0;
          img {
            cursor: pointer;
            transition: all 0.4s linear;
            filter: brightness(0.8);
            &:hover {
              filter: brightness(1.2);
            }
          }
          @media screen and (min-width: 848px) and (max-width: 1024px) {
            min-width: 50vw;
          }
        }
        &.three {
          button {
            outline: none;
            border: 1.5px solid var(--main-color);
            text-align: center;
            padding: 15px 40px;
            color: var(--light-green);
            font-weight: bold;
            letter-spacing: 1px;
            font-size: 16px;
            line-height: 16px;
            background: rgba(87, 19, 21, 0.4);
            transition: all 0.5 linear;
            cursor: pointer;
            filter: brightness(0.8);
            &:hover {
              filter: brightness(1.2);
            }
          }
        }
        img {
          width: 200px;
          object-fit: contain;
        }
      }
    }
  }
  .img-footer {
    width: 100%;
    bottom: 0;
    margin-top: 80px;
    img {
      width: 100%;
      object-fit: contain;
    }
  }
}
</style>
