<template>
  <div class="roadmap-wrapper">
    <div class="roadmap-contain-img">
      <div class="grid">
        <img :src="Artboard29" alt="" />
      </div>
    </div>
    <div class="backer-title">
      <img :src="Artboard75_1" alt="" />
    </div>
  </div>
</template>

<script>
import Artboard29 from "../assets/images/Artboard 29.png";
import Artboard75_1 from "../assets/images/Artboard 75_1.png";
export default {
  name: "RoadmapComponent",
  data() {
    return {
      Artboard29,
      Artboard75_1,
    };
  },
};
</script>

<style lang="scss" scoped>
.roadmap-wrapper {
  background-image: url("../assets/images/Artboard 36.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: top center;
  display: flex;
  align-items: center;
  flex-direction: column;
  .roadmap-contain-img {
    margin-top: 260px;
    background-image: url("../assets/images/Artboard 41.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: top center;
    width: 100%;
    display: flex;
    justify-content: center;
    .grid {
      max-width: 1200px;
      img {
        width: 100%;
        object-fit: contain;
      }
    }
  }
  .backer-title {
    margin: 100px 0;
    img {
      max-width: 320px;
      object-fit: contain;
    }
  }
}
</style>
