<template>
  <div id="bottomLeft">
    <div class>
      <div class="d-flex pt-2 pl-2">
        <span style="color:#5cd9e8">
          <icon name="chart-bar"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">构建统计图</span>
        </div>
      </div>
      <div>
        <bottomLeftChart />
      </div>
    </div>
  </div>
</template>

<script>
import bottomLeftChart from "@/components/echart/bottom/bottomLeftChart";
export default {
  data() {
    return {};
  },
  components: {
    bottomLeftChart
  },
  mounted() {
  },
  methods: {}
};
</script>

<style lang="scss">
#bottomLeft {
  padding: 1rem;
  height: 410px;
  min-width: 300px;
  border-radius: 5px;
  .bg-color-black {
    height: 385px;
    border-radius: 10px;
  }
  .text {
    color: #c3cbde;
  }
  .chart-box {
    margin-top: 1rem;
    width: 170px;
    height: 170px;
    .active-ring-name {
      padding-top: 10px;
    }
  }
}
</style>