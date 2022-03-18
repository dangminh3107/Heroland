<template>
  <div class="footer-wrapper">
    <div class="footer-grid">
      <div class="title-footer">
        <img :src="Artboard92" alt="" />
      </div>
      <div class="item">
        <div class="title">
          <img :src="Artboard93" alt="" />
        </div>
        <ul>
          <li v-for="(item, index) in about" :key="index">{{ item }}</li>
        </ul>
      </div>
      <div class="item">
        <div class="title">
          <img :src="Artboard95" alt="" />
        </div>
        <ul>
          <li v-for="(item, index) in menu" :key="index">{{ item }}</li>
        </ul>
      </div>
      <div class="item">
        <div class="title">
          <img :src="Artboard96" alt="" />
        </div>
        <ul>
          <li v-for="(item, index) in info" :key="index">{{ item }}</li>
          <div class="button">
            <img :src="Artboard64" alt="" />
          </div>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Artboard64 from "../assets/images/Artboard 64.png";
import Artboard92 from "../assets/images/Artboard 92.png";
import Artboard93 from "../assets/images/Artboard 93.png";
import Artboard95 from "../assets/images/Artboard 95.png";
import Artboard96 from "../assets/images/Artboard 96.png";
export default {
  name: "FooterComponent",
  data() {
    return {
      about: [
        "HBG overview",
        "Project overview",
        "Token Metric",
        "Whitepapper",
      ],
      menu: [
        "Home",
        "About",
        "Base",
        "Benefit",
        "Tokenomic",
        "Roadmap",
        "Partner",
        "Community",
      ],
      info: ["Official Token", "Help Center"],
      Artboard92,
      Artboard93,
      Artboard95,
      Artboard96,
      Artboard64,
    };
  },
};
</script>

<style lang="scss" scoped>
.footer-wrapper {
  width: 100%;
  display: flex;
  justify-content: center;
  background-image: url("../assets/images/Artboard 83.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top center;
  padding: 80px 0 130px;
  color: var(--white-color);
  font-size: 20px;
  .footer-grid {
    width: 1200px;
    display: flex;
    justify-content: space-between;
    padding: 0 20px;
    @media screen and (max-width: 860px) {
      flex-direction: column;
      width: unset;
    }
    .title-footer {
      position: relative;
      top: -6px;
      img {
        max-height: 36px;
        object-fit: contain;
      }
    }
    .item {
      @media screen and (max-width: 860px) {
        margin-bottom: 30px;
      }
      .title {
        margin-bottom: 30px;
        img {
          max-height: 30px;
          object-fit: contain;
        }
      }
      ul {
        list-style: none;
        li {
          padding-bottom: 5px;
        }
        .button {
          margin-top: 20px;
          position: relative;
          left: -10px;
          img {
            max-width: 200px;
            object-fit: contain;
          }
        }
      }
    }
  }
}
</style>
