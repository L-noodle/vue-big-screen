<template>
  <div id="bottomRight">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span style="color:#5cd9e8">
          <icon name="chart-area"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">工单修复以及满意度统计图</span>
          <div class="decoration2">
            <dv-decoration-2 :reverse="true" style="width:5px;height:480px;" />
          </div>
        </div>
      </div>
      <div>
        <bottomRightChart />
      </div>
    </div>
  </div>
</template>

<script>
import bottomRightChart from "@/components/echart/bottom/bottomRightChart";
export default {
  data() {
    return {};
  },
  components: {
    bottomRightChart
  },
  mounted() {},
  methods: {}
};
</script>

<style lang="scss">
#bottomRight {
  padding: 1rem 1rem 0rem;
  height: 520px;
  min-width: 300px;
  border-radius: 5px;
  .bg-color-black {
    height: 495px;
    border-radius: 10px;
  }
  .text {
    color: #c3cbde;
  } //下滑线动态
  .decoration2 {
    position: absolute;
    right: 10px;
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