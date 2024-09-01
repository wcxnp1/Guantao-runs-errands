<template>
  <div class="EnterpriseOptions">
    <div class="EnterpriseOptions__action">
      <div class="EnterpriseOptions__action-img">

        <img src="../assets/image/one.jpg" alt="" style="width: 100%;height: 100%;">

        <!-- <img src="../assets/image/one.jpg" alt="" style="width: 100%;height: 100%;z-index: -999;"> -->
      </div>
      <!-- <div class="EnterpriseOptions__action-img">
              <img src="../assets/image/one.jpg" alt="" style="width: 100%;height: 100%;z-index: -999;">
              <div class="EnterpriseOptions__title">
                  <p>全行业定制化配送解决方案 服务无忧 体验更优</p>
                  <span>超过2000000+来自不同行业的商家选择使用UU跑腿</span>
              </div>
          </div> -->

    </div>
    <div class="EnterpriseOptions__content">
      <!-- <ul>
              <template v-for="item in options " :key="item.id">
                  <li @mouseover="toggleBox" class="colorset">
                      <img :src="item.img" alt="">
                      <span>{{ item.title }}</span>
                  </li>
              </template>

</ul>
<transition name="fade">
  <div class="EnterpriseOptions__content-butom" :class="{ 'move-up': isBoxVisible }"></div>
</transition> -->
    </div>
  </div>
</template>
<script>


export default {
  name: 'EnterpriseOptions',

  data() {
    return {
      options: [
        {
          id: 1,
          title: '外卖餐饮配送',
          img: require('../../public/icon_sbise1yjovh/24gf-bag.png')
        },
        {
          id: 2,
          title: '鲜花配送',
          img: require('../../public/icon_sbise1yjovh/chufadihedidian.png')
        },
        {
          id: 3,
          title: '3c数码配送',
          img: require('../../public/icon_sbise1yjovh/dangao.png')
        },
        {
          id: 4,
          title: '蛋糕配送',
          img: require('../../public/icon_sbise1yjovh/tel.png')
        }

      ],

      isBoxVisible: false,
      isAnimating: false
    }
  },
  methods: {
    toggleBox() {
      if (this.isAnimating) return; // 如果正在动画中，直接返回
      this.isAnimating = true;
      this.isBoxVisible = true;
      setTimeout(() => {
        this.isBoxVisible = false;
        setTimeout(() => {
          this.isAnimating = false; // 动画结束后重置 isAnimating
        }, 300); // 等待动画结束后重置 isAnimating
      }, 300); // 只保留上移的动画效果
    }
  }


}
</script>
<style scoped lang="scss">
.EnterpriseOptions {
  width: 100%;
  height: 800px;
  margin-top: 150px;
  position: relative;
  // background-color: aqua;
  overflow: hidden;

  .EnterpriseOptions__action {
    height: 50%;
    width: 100%;
    position: relative;

    .EnterpriseOptions__action-img {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      z-index: 999;
    }

    // background-color: #ff6900;
    // .EnterpriseOptions__action-img {
    //     position: absolute;
    //     left: 0;
    //     top: 0;
    //     width: 100%;
    //     height: 100%;
    //     // background-color: red;
    //     // z-index: 9999;
    //     background-color: rgba(0, 0, 0, 0.5);
    // }

    // .EnterpriseOptions__title {
    //     position: absolute;
    //     left: 50%;
    //     top: 25%;
    //     text-align: center;
    //     transform: translate(-50%, -50%);
    //     color: white;
    // }

    // .EnterpriseOptions__title>p {
    //     font-size: 35px;
    //     font-weight: 900;
    //     margin-bottom: 10px;
    // }

    // .EnterpriseOptions__title>span {
    //     font-size: 18px;
    //     color: #9eaaae;

    // }
  }

  .EnterpriseOptions__content {
    width: 60%;
    height: 100%;
    position: absolute;
    top: -28%;
    left: 50%;
    transform: translateX(-50%);
    bottom: 280px;
    position: relative;
    animation: none;

    /* 初始时不播放动画 */
    ul {
      width: 100%;
      height: 100px;
      display: flex;
      justify-content: space-around;

      li {
        width: 25%;
        height: 100%;
        border: 1px solid white;
        display: flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        -moz-box-sizing: border-box;
        -webkit-box-sizing: border-box;

        img {
          width: 30px;
          height: 25px;
          padding-right: 5px;
        }

        span {
          font-size: 20px;
          color: white;
          font-weight: 700;
        }
      }

      // li:hover {
      //     background-color: #ff6900;
      //     border: none;
      // }

      // li:hover span {
      //     transform: scale(1.2);
      //     margin-left: 10px;
      // }

      // li:hover img {
      //     transform: scale(1.2);
      // }

      li:nth-child(1) {
        border-right: none;
      }

      li:nth-child(2) {
        border-right: none;
      }

      li:nth-child(3) {
        border-right: none;
      }
    }

    .EnterpriseOptions__content-butom {
      transition: transform 0.5s;
      margin-top: 30px;
      width: 100%;
      height: 100%;
      background-color: #ff6900;
    }

  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.move-up {
  transform: translateY(100px);
  transition: transform 0.2s;
}
</style>