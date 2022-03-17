<template>
  <div class="nav-bar">
    <div class="img-contain">
      <a href="">
        <img :src="Artboard10" alt="" />
      </a>
    </div>
    <div class="nav-item">
      <ul>
        <li
          :class="{ active: clickedItem === index }"
          @click="handleClick(index)"
          v-for="(item, index) in navItem"
          :key="index"
        >
          {{ item }}
        </li>
      </ul>
      <div class="avatar">
        <img :src="Artboard12" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
  import Artboard10 from "../assets/images/Artboard 10.png";
  import Artboard12 from "../assets/images/Artboard 12.png";
export default {
  name: "NavbarComponent",
  data() {
    return {
      clickedItem: 0,
      navItem: [
        "Home",
        "About",
        "Base",
        "Benefit",
        "Tokenomic",
        "Roadmap",
        "Partner",
        "Comunity",
        "Launch App",
      ],
      Artboard10,
      Artboard12,
    };
  },
  methods: {
    handleClick(index) {
      // this.$emit("item-context", true);
      this.clickedItem = index;
    },
  },
};
</script>

<style lang="scss">
.nav-bar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 100px;
  background-color: #000;
  display: flex;
  align-items: center;
  justify-content: space-around;
  z-index: 99;
  .nav-item {
    display: flex;
    align-items: center;
    ul {
      list-style: none;
      color: var(--main-color-deactive);
      font-weight: bold;
      display: flex;
      align-items: center;
      font-size: 18px;
      li {
        padding: 0 10px;
        cursor: pointer;
        transition: all 0.5s;
        &:hover {
          color: var(--main-color);
        }
        &.active {
          color: var(--main-color);
        }
      }
      @media screen and (min-width: 848px) and (max-width: 1024px) {
        font-size: 1.5vw;
      }

      @media screen and (max-width: 848px) {
        display: none;
      }
    }
    .avatar {
      width: 30px;
      height: 30px;
      margin-left: 10px;
      img {
        width: 100%;
        object-fit: contain;
      }
      @media screen and (max-width: 848px) {
        display: none;
      }
    }
  }
  .img-contain {
    img {
      cursor: pointer;
      width: 100px;
      object-fit: contain;

      @media screen and (min-width: 848px) and (max-width: 1024px) {
        width: 80px;
        object-fit: contain;
      }

      @media screen and (max-width: 848px) {
        width: 60px;
        object-fit: contain;
      }
    }
  }
  @media screen and (max-width: 848px) {
    justify-content: center;
    height: 80px;
  }
}
</style>
