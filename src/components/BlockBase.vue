<template>
  <div class="block-base">
    <HeroBase :pos="pos"/>
    <ElectricBase :pos="pos"/>
  </div>
</template>

<script>
import HeroBase from "./HeroBase.vue";
import ElectricBase from "./ElectricBase.vue";
export default {
  name: "BlockBaseComponent",
  props: ['pos'],
  components: {
    HeroBase,
    ElectricBase,
  },
};
</script>

<style lang="scss" scoped>
.block-base {
  width: 100%;
  padding-bottom: 300px;
  background-image: url("../assets/images/Artboard 24.png");
  background-repeat: no-repeat;
  background-size: 100% 100%;
  background-position: center;
  display: flex;
  align-items: center;
  flex-direction: column;
  @media screen and (max-width: 970px) {
    background-size: cover;
  }
}
</style>
