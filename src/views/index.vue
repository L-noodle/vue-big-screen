<template>
  <div id="index">
    <dv-full-screen-container class="bg">
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div class="host-body">
        <div class="d-flex jc-center">
          <dv-decoration-10 style="width:33.3%;height:5px;" />
          <div class="d-flex jc-center">
            <dv-decoration-8 :color="['#568aea', '#000000']" style="width:200px;height:50px;" />
            <div class="title">
              <span class="title-text">SKCI数据可视化平台</span>
              <dv-decoration-6
                class="title-bototm"
                :reverse="true"
                :color="['#50e3c2', '#67a1e5']"
                style="width:250px;height:8px;"
              />
            </div>
            <dv-decoration-8
              :reverse="true"
              :color="['#568aea', '#000000']"
              style="width:200px;height:50px;"
            />
          </div>
          <dv-decoration-10 style="width:33.3%;height:5px;" />
        </div>

        <!-- 第二行 -->
        <div class="d-flex jc-between mt-2 px-2">
          <div class="d-flex" style="width: 40%">
            <div class="react-right bg-color-black ml-4" style="width: 500px; ">
              <span class="react-before"></span>
              <span class="text">构建数据分析</span>
            </div>
            <div class="react-right bg-color-black ml-3">
              <span class="text colorBlue">构建数据分析</span>
            </div>
          </div>
          <div style="width: 40%" class="d-flex">
            <div class="react-left bg-color-black bg-color-blue mr-3">
              <span class="text fw-b">构建数据分析</span>
            </div>
            <div class="react-left bg-color-black mr-4" style="width: 500px;">
              <span class="react-after"></span>
              <span class="text colorBlue">2020年03月16日</span>
            </div>
          </div>
        </div>

        <div class="body-box">
          <!-- 第三行数据 -->
          <div class="content-box">
            <div>
              <dv-border-box-12>
                <centreLeft1 />
              </dv-border-box-12>
            </div>
            <div></div>
            <div class="bg-color-blue"></div>
            <div></div>
            <div class="bg-color-blue"></div>
            <div></div>
          </div>

          <!-- 第四行数据 -->
          <div class="bototm-box">
            <div></div>
            <div></div>
          </div>
        </div>
      </div>
    </dv-full-screen-container>
  </div>
</template>

<script>
import centreLeft1 from "./centreLeft1";
export default {
  data() {
    return {
      loading: false
    };
  },
  components: { centreLeft1 },
  mounted() {
    this.cancelLoading();
  },
  methods: {
    cancelLoading() {
      setTimeout(() => {
        this.loading = false;
      }, 2000);
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/index.scss";
</style>