<template>
  <div class="ecosystem">
    <div class="eco-grid">
      <div class="title">
        <img :src="Artboard76" alt="" />
      </div>
    </div>
    <div class="content">
      <div class="eco-grid">
        <table>
          <tr v-for="(item, index) in textArr" :key="index">
            <td class="percent" :style="{ color: color[index] }">
              <h1 v-html="item.percent"></h1>
            </td>
            <td class="text">
              <p v-html="item.text"></p>
            </td>
          </tr>
        </table>
        <div class="pie-chart">
          <img :src="Artboard39" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Artboard76 from "../assets/images/Artboard 76.png";
import Artboard39 from "../assets/images/Artboard 39.png";
export default {
  name: "HBGEcosystemCompoent",
  data() {
    return {
      textArr: [
        {
          percent: "3<span>%</span>",
          text: `on Airdrop campaign and marketing promotion - <span>30,000,000 Tokens</span>`,
        },
        {
          percent: "15<span>%</span>",
          text: `Pre-Sale Release - <span>150,000,000 Tokens</span>`,
        },
        {
          percent: "5<span>%</span>",
          text: `under the management of the Advisory Board - <span>50,000,000 Tokens</span>`,
        },
        {
          percent: "15<span>%</span>",
          text: `listed on reserve fund and exchange - <span>150,000,000 Tokens</span>`,
        },
        {
          percent: "25<span>%</span>",
          text: `for P2E - accompanying ecosystem - <span>250,000,000 Tokens</span>`,
        },
        {
          percent: "15<span>%</span>",
          text: `under the management of the development team and ecosys-tem administrator - <span>150,000,000 Tokens</span>`,
        },
        {
          percent: "12<span>%</span>",
          text: `for international marketing and expansion - <span>120,000,000 Tokens</span>`,
        },
        {
          percent: "10<span>%</span>",
          text: `for project development fund - <span>100,000,000 Tokens</span>`,
        },
      ],
      color: [
        "#EDEDED",
        "#00FF60",
        "#7DD2CB",
        "#C30000",
        "#D56969",
        "#ACDC00",
        "#849040",
        "#586198",
      ],
      Artboard76,
      Artboard39,
    };
  },
};
</script>

<style lang="scss">
.ecosystem {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: hidden;
  bottom: -160px;
  .eco-grid {
    width: 1200px;
    .title {
      img {
        max-width: 650px;
        @media screen and (max-width: 660px) {
          max-width: 90vw;
        }
      }
    }
    @media screen and (max-width: 1200px) {
      width: unset;
    }
  }
  .content {
    display: flex;
    width: 100%;
    justify-content: center;
    background-image: url("../assets/images/Artboard 82.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: top center;
    align-items: center;
    padding: 40px 0 20px;
    .eco-grid {
      padding: 0 30px;
      display: flex;
      max-width: 1200px;
      @media screen and (max-width: 900px) {
        flex-direction: column;
        align-items: center;
      }
      table {
        padding-right: 50px;
        @media screen and (max-width: 650px) {
          padding-right: 0;
        }
        tr {
          .percent {
            padding-right: 20px;
            padding-bottom: 10px;
            h1 {
              font-size: 36px;
              @media screen and (max-width: 650px) {
                font-size: 7vw;
              }
              line-height: 36px;
              display: inline-block;
              span {
                font-size: 22px;
              }
            }
          }
          .text {
            color: var(--white-color);
            font-size: 18px;
            @media screen and (max-width: 650px) {
              font-size: 2.4vw;
            }
            span {
              font-weight: bold;
            }
          }
        }
        @media screen and (max-width: 900px) {
          margin-bottom: 20px;
        }
      }
      .pie-chart {
        img {
          max-width: 350px;
        }
      }
    }
  }
}
</style>
