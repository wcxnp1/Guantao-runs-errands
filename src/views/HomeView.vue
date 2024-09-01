<template>
  <div class="hello">
    <div class="header">
      <div class="header-box">
        <!--  第一块 -->
        <div class="header-box-left">
          <p class="headername">观涛跑腿</p>
          <span class="headtext">同城急事 找观涛跑腿</span>
        </div>
        <!--  -->
        <ul class="header-box-center">
          <li>首页</li>
          <li>服务介绍</li>
          <li>开发平台</li>
          <li>UU家政</li>
          <li>UU运货</li>
          <li @mouseover="handleMouseOver" @mouseout="handleMouseOut" class="setli">加入我们
          </li>
          <div class="Joinus" v-show="isShow">
            <li>加盟跑腿</li>
            <li>成为跑男</li>
            <li>人才招聘</li>
            <li>加盟货运</li>
          </div>
          <li class="UIset" @mouseover="handleMouseOverUIset" @mouseout="handleMouseOutUIset">关于UU</li>
          <div class="UIsetchilie" v-show="UIset">
            <li>加盟跑腿</li>
            <li>成为跑男</li>
            <li>人才招聘</li>
            <li>加盟货运</li>
          </div>
        </ul>
        <!--  -->
        <div class="header-box-right">
          <div class="swrpositioning">
            <img src="../assets/dingwei.png" alt="">
            <span>定位失败</span>
          </div>
          <div class="btn">
            <button>企业版</button>
            <button>商家版</button>
          </div>
        </div>
      </div>

    </div>
    <Carousel></Carousel>
    <commercial></commercial>
    <salesmanship></salesmanship>
    <EnterpriseOptions></EnterpriseOptions>
  </div>
</template>

<script>
// @ is an alias to /src
// 轮播图
import Carousel from "@/components/Carousel.vue"
// 广告commercial
import commercial from "@/components/commercial.vue"
// 推销 salesmanship
import salesmanship from "@/components/salesmanship.vue"
// 企业选项
import EnterpriseOptions from "@/components/EnterpriseOptions.vue"
export default {
  name: 'HelloWorld',
  data() {
    return {
      isShow: false,
      UIset: false
    }
  },
  methods: {
    handleMouseOver() {
      this.isShow = !this.isShow
    },
    handleMouseOut() {
      this.isShow = !this.isShow
    },
    handleMouseOverUIset() {
      this.UIset = !this.UIset
    },
    handleMouseOutUIset() {
      this.UIset = !this.UIset

    }
  },
  components:{
    Carousel,
    commercial,
    salesmanship,
    EnterpriseOptions
  }
}
</script>

<style scoped lang="scss">
.hello {
  width: 100%;
  height: 100%
}

.cntent {
  margin-top: 100px;
  width: 100vw;
  height: 100px;
  background: gold;
}
</style>
