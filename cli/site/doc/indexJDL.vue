<template>
  <div class="container">
    <span class="nut-big"></span>
    <span class="circle-big"></span>
    <span class="circle"></span>
    <span class="square"></span>
    <span class="nut-small"></span>
    <template v-if="notWebgl">
      <div class="css-animation">
        <span class="backcolor"></span>
        <span class="phone1"></span>
        <span class="phone2"></span>
        <span class="phone3"></span>
        <span class="phone4"></span>
        <span class="phone5"></span>
      </div>
    </template>
    <template v-else>
      <canvas id="output"></canvas>
    </template>
    <div class="wrapper">
      <div class="header">
        <span class="logo">
          NUTUI
          <s></s>
        </span>
        <search />

        <div class="menu">
          <ul>
            <li>
              <a href="#/intro">指南</a>
            </li>
            <li>
              <a href="#/ActionSheet">组件</a>
            </li>
            <li>
              <a href="#/design">资源</a>
            </li>
            <li>
              <a href="/demo.html#/index" class="qrcode top-qr" target="_blank">
                示例
                <a>
                  <span>请使用手机扫码体验</span>
                  <img
                    src="https://img12.360buyimg.com/imagetools/jfs/t1/124892/31/7144/6065/5f0d9fe4Ef020d678/cae78d015aa5897c.png"
                    alt />
                </a>
              </a>
            </li>
          </ul>
          <doc-ecology></doc-ecology>
          <doc-version></doc-version>
          <a href="https://github.com/jdf2e/nutui" title="Github" target="_blank" class="github-icon">github</a>
        </div>
      </div>
      <div class="content">
        <div class="mouseDiv" id="mouseDiv"></div>
        <p class="title">NutUI-JDL</p>
        <p class="sub-title">京东物流风格的轻量级移动端Vue组件库</p>
        <div style="display: flex;align-items: center;">
          <a href="#/intro" class="blue-btn">开始使用</a>
          <a href="javascript:;" class="qrcode btn">
            扫码体验
            <a>
              <span>请使用手机扫码体验</span>
              <img
                src="https://img12.360buyimg.com/imagetools/jfs/t1/124892/31/7144/6065/5f0d9fe4Ef020d678/cae78d015aa5897c.png"
                alt />
            </a>
          </a>
          <iframe style="margin-left:20px" src="https://ghbtns.com/github-btn.html?user=jdf2e&repo=nutui&type=star&count=true&size=large"
            frameborder="0" scrolling="0" width="170" height="30" title="GitHub"></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import search from "./search.vue";
export default {
  name: "frontCover_v3",
  data() {
    return {
      timer: null,
      notWebgl: true,
      isSmall: false
    };
  },
  components: {
    search
  },
  methods: {},
  watch: {},
  computed: {},
  created() {},
  mounted() {
    this.$nextTick(() => {
      //获取浏览器宽度
      let windowWidth = document.body.clientWidth;
      if (windowWidth <= 990) {
        this.isSmall = true;
      }

      this.notWebgl = true;
      // if (!Detector.webgl) {
      //   //Detector.addGetWebGLMessage();
      // } else {
      //   this.notWebgl = false;
      //   this.threeAnimation();
      // }
    });
  },
  destroyed() {}
};
</script>
<style lang="scss" scoped>
@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translate3d(-100%, 0, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes phoneIn {
  from {
    opacity: 0;
    transform: translate3d(-100%, 100%, 0);
  }
  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes leftToRight {
  from {
    transform: translate3d(-20px, 0, 0);
  }
  to {
    transform: translate3d(0, 0, 0);
  }
}

@keyframes upToBottom {
  from {
    transform: translate3d(0, -20px, 0);
  }
  to {
    transform: translate3d(0, 0, 0);
  }
}

@keyframes incline {
  from {
    transform: translate3d(-100px, -50px, 0);
  }
  to {
    transform: translate3d(0, 0, 0);
  }
}

@keyframes rotateSelf {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(360deg);
  }
}

.container {
  position: relative;
  min-width: 1260px;
  height: 100vh;
  overflow: hidden;
  .nut-big {
    position: absolute;
    top: -14.2vh;
    left: 57.8vh;
    width: 59.7vh;
    height: 59.7vh;
    background: url(./asset/img/v3-nut-big.png) 0 0 no-repeat;
    background-size: 100% 100%;
  }
  .circle-big {
    position: absolute;
    margin-left: -28.7vh;
    top: 50.6vh;
    left: 0;
    width: 46.7vh;
    height: 46.7vh;
    background: url(./asset/img/v3-circle-big.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: leftToRight 2s alternate infinite;
  }
  .circle {
    position: absolute;
    top: 55vh;
    margin-left: 54.4vh;
    left: 0;
    width: 15.8vh;
    height: 15.8vh;
    background: url(./asset/img/v3-circle.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: incline 4s alternate infinite both;
  }
  .square {
    position: absolute;
    left: 46vh;
    bottom: -10.1vh;
    width: 22.6vh;
    height: 22.6vh;
    background: url(./asset/img/v3-square.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: upToBottom 2s alternate infinite both;
  }
  .nut-small {
    position: absolute;
    bottom: 2.8vh;
    right: 5.3vh;
    width: 15.8vh;
    height: 15.8vh;
    background: url(./asset/img/v3-nut-small.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: rotateSelf 3s linear 1s infinite both;
  }
  .backcolor {
    position: absolute;
    top: 2.7vh;
    right: 0;
    width: 125vh;
    height: 102vh;
    background: url(./asset/img/v3-backcolor.png) 0 0 no-repeat;
    background-size: 100% 100%;
  }
  .phone1 {
    position: absolute;
    right: 13.1vh;
    top: 14.6vh;
    width: 43.6vh;
    height: 46.6vh;
    background: url(./asset/img/v3-phone1.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: phoneIn 0.5s both;
  }
  .phone2 {
    position: absolute;
    right: 46vh;
    top: 18.2vh;
    width: 43.6vh;
    height: 46.6vh;
    background: url(./asset/img/v3-phone2.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: phoneIn 0.5s 0.1s both;
  }
  .phone3 {
    position: absolute;
    top: 48.2vh;
    right: 11.84vh;
    width: 43.6vh;
    height: 46.6vh;
    background: url(./asset/img/v3-phone3.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: phoneIn 0.5s 0.2s both;
  }
  .phone4 {
    position: absolute;
    top: 49.9vh;
    right: 43.3vh;
    width: 43.5vh;
    height: 46.5vh;
    background: url(./asset/img/v3-phone4.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: phoneIn 0.5s 0.3s both;
  }
  .phone5 {
    position: absolute;
    top: 54vh;
    right: 75.8vh;
    width: 43.54vh;
    height: 46.6vh;
    background: url(./asset/img/v3-phone5.png) 0 0 no-repeat;
    background-size: 100% 100%;
    animation: phoneIn 0.5s 0.4s both;
  }
}
.wrapper {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;

  .header {
    top: 0;
    min-width: 990px;
    width: 100%;
    height: 64px;
    display: flex;
    align-items: center;
    position: relative;
  }
  .menu {
    position: absolute;
    top: 0;
    right: 100px;
    width: 370px;
    font-size: 14px;
    display: flex;
    align-items: center;
    li {
      float: left;
      width: 70px;
      text-align: center;
      height: 64px;
      line-height: 64px;
      cursor: pointer;
      color: rgba(51, 51, 51, 1);
      position: relative;
      & > a {
        display: block;
        height: 100%;
        line-height: 64px;
      }
      a {
        color: rgba(51, 51, 51, 1);
        text-decoration: none;
      }
    }

    li::before {
      content: "";
      position: absolute;
      top: 0;
      left: 100%;
      width: 0;
      height: 100%;
      border-bottom: 2px solid #fff;
      transition: 0.2s all linear;
    }
    li:hover:before {
      width: 100%;
      top: 0;
      left: 0;
      transition-delay: 0.1s;
      border-bottom-color: #fff;
      z-index: -1;
    }
    li:hover ~ li::before {
      left: 0;
    }
    .github-icon {
      display: inline-block;
      height: 26px;
      width: 26px;
      font-size: 0;
      // background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' height='24' viewBox='0 0 16 16' version='1.1' width='24' aria-hidden='true'%3E%3Cpath fill-rule='evenodd' fill='rgb(255,255,255)' d='M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z'%3E%3C/path%3E%3C/svg%3E")
      //   no-repeat;
      background: url(./asset/img/v3-github-logo.png) 0 0 no-repeat;
      background-size: 100% 100%;
      vertical-align: middle;
      position: relative;
      top: -1px;
      margin-left: 35px;
      cursor: pointer;
      &:hover,
      &:active {
        opacity: 0.7;
      }
    }
  }
  .logo {
    height: 100%;
    line-height: 64px;
    float: left;
    width: 245px;
    font-size: 0;
    position: relative;
    s {
      background: url(./asset/img/nutui-jdl.png) 0 0 no-repeat;
      background-size: contain;
      height: 46px;
      width: 180px;
      display: inline-block;
      position: absolute;
      top: 50%;
      left: 50px;
      margin-top: -23px;
    }
  }
  .search {
    margin: 20px 0;
    display: inline-block;
    border-left: 1px solid #d8d8d8;
    padding-left: 84px;
    position: relative;
    &:before {
      content: "";
      display: inline-block;
      background: url(./asset/img/search.png) 0 0 no-repeat;
      height: 22px;
      width: 22px;
      position: absolute;
      top: 50%;
      margin-top: -11px;
      left: 40px;
    }
    .search-input {
      border: none;
      height: 24px;
      line-height: 24px;
      font-size: 12px;
      outline: none;
      width: 200px;
      background: transparent;
    }
  }
  .content {
    padding: 12% 0 0 8.8%;
    z-index: 999;
    position: relative;
    .mouseDiv {
      height: 300px;
      width: 500px;
      //background:#ccc;
      position: absolute;
      top: 50%;
      left: 50%;
      margin-left: -250px;
      margin-top: -50px;
    }
    .title {
      font-size: 42px;
      color: #333;
      font-weight: bold;
      animation: fadeInLeft 1s both;
    }
    .sub-title {
      font-size: 24px;
      color: #333;
      padding-top: 13px;
      padding-bottom: 26px;
      animation: fadeInLeft 1s both 0.5s;
    }
    .btn,
    .blue-btn {
      border: 1px solid rgba(9, 69, 255, 1);
      background: #fff;
      color: rgba(9, 69, 255, 1);
      width: 150px;
      height: 40px;
      line-height: 40px;
      text-align: center;
      display: inline-block;
      font-size: 14px;
      text-decoration: none;
      border-radius: 25px;
      animation: fadeInLeft 1s both 1.2s;
      &:hover,
      &:active {
        border-color: rgba(9, 69, 255, 0.8);
        color: rgba(9, 69, 255, 0.8);
      }
    }
    .blue-btn {
      border: none;
      color: #fff;
      background: linear-gradient(
        130deg,
        rgba(36, 116, 255, 1) 0%,
        rgba(4, 47, 255, 1) 100%
      );
      margin-right: 26px;
      &:hover,
      &:active {
        background: linear-gradient(
          130deg,
          rgba(36, 116, 255, 0.8) 0%,
          rgba(4, 47, 255, 0.8) 100%
        );
        color: rgba(255, 255, 255, 0.8);
      }
    }
    iframe{
			animation: fadeInLeft 1s both 1.2s;
		}
  }
  .qrcode {
    background: none;
    width: auto;
    margin: 0;
    opacity: 1;
    &.top-qr {
      a {
        left: -65px;
        top: 60px;
      }
    }
    a {
      position: absolute; //display: none;
      top: 50px;
      width: 200px;
      height: 240px;
      transform: scale(0.5);
      transform-origin: 50% top 0;
      transition: all 100ms ease-in-out 50ms;
      background: url("./asset/img/kuang.png") no-repeat;
      background-size: 200px;
      text-decoration: none;
      font-style: normal;
      text-align: center;
      left: -35px;
      overflow: hidden;
      pointer-events: none;
      span {
        display: block;
        overflow: hidden;
        color: #666;
        font-size: 14px;
        text-align: center;
        height: 45px;
        width: 100%;
        line-height: 60px;
      }
      img {
        opacity: 0.8;
        width: 166px;
        height: 166px;
      }
    }
    &:hover {
      opacity: 1;
      a {
        display: inline-block;
        opacity: 1;
        transform: scale(1);
      }
    }
  }
}

.css-animation {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 1140px;
  animation: fadeInRightAndTop 1.2s 1;
  transform: scale3d(1.06, 1.06, 1.06);
}
@media screen and (max-width: 1500px) {
  .css-animation {
    .blue-bg {
      transform: translateX(155px);
    }
  }
  .wrapper {
    .content {
      padding-left: 5%;
    }
    .menu {
      right: 6%;
    }
  }
}
</style>
