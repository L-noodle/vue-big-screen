<template>
  <div id="center">
    <div class="up">
      <div class="bg-color-black item" v-for="item in titleItem" :key="item.title">
        <p class="ml-3 fs-xl">{{item.title}}</p>
        <div>
          <dv-digital-flop :config="item.number" style="width:100px;height:50px;" />
        </div>
      </div>
    </div>
    <div class="down">
      <div class="ranking">
        <dv-scroll-ranking-board :config="ranking"/>
      </div>
      <div class="percent">
        <div class="item"> </div>
        <div class="water">
          <dv-water-level-pond :config="water" style="height: 125px" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titleItem: [
        {
          title: "今年累计构建次数",
          number: {
            number: [120],
            toFixed: 1,
            content: "{nt}"
          }
        },
        {
          title: "本月累计构建次数",
          number: {
            number: [18],
            toFixed: 1,
            content: "{nt}"
          }
        },
        {
          title: "今日累计构建次数",
          number: {
            number: [2],
            toFixed: 1,
            content: "{nt}"
          }
        },
        {
          title: "今年失败构建次数",
          number: {
            number: [14],
            toFixed: 1,
            content: "{nt}"
          }
        },
        {
          title: "今年成功构建次数",
          number: {
            number: [106],
            toFixed: 1,
            content: "{nt}"
          }
        },
        {
          title: "今年达标组件个数",
          number: {
            number: [100],
            toFixed: 1,
            content: "{nt}"
          }
        }
      ],
      ranking: {
        data: [
          {
            name: "周口",
            value: 55
          },
          {
            name: "南阳",
            value: 120
          },
          {
            name: "西峡",
            value: 78
          },
          {
            name: "驻马店",
            value: 66
          },
          {
            name: "新乡",
            value: 80
          },
          {
            name: "新乡",
            value: 80
          },
          {
            name: "新乡",
            value: 80
          },
          {
            name: "新乡",
            value: 80
          }
        ],
        waitTime: 4000,
        carousel: "page",
        unit: "份"
      },
      water: {
        data: [24, 45]
      }
    };
  }
};
</script>

<style lang="scss" scoped>
#center {
  display: flex;
  flex-direction: column;
  .up {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    .item {
      border-radius: 5px;
      padding-top: 1rem;
      margin-top: 0.5rem;
      width: 32%;
      height: 70px;
    }
  }
  .down {
    padding: 0.5rem;
    padding-bottom: 0px;
    width: 100%;
    display: flex;
    height: 250px;
    justify-content: space-between;
    .ranking {
      width: 58%;
    }
    .percent {
      width: 40%;
      display: flex;
      flex-direction: column;
      .item {
        width: 100%;
        height: 125px;
      }
      .water {
        width: 100%;
      }
    }
  }
}
</style>