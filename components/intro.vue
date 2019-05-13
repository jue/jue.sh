<template>
  <div class="container-intro">
    <pageTitle :pTitle="'首页'"></pageTitle>
    <div class="main">
      <div class="intro">
        <span>专注产品研发、技术创新</span>
        <span>
          我们从事
          <vue-typed-js
            :backSpeed="100"
            :cursorChar="'_'"
            :loop="true"
            :strings="strings"
            :typeSpeed="100"
          >
            <strong class="typing"></strong>
          </vue-typed-js>
        </span>
        <span>一个专注互联网技术开发的供应商</span>
      </div>
      <div class="flex1"></div>
      <div class="intro-text">
        <span>
          致力于为客户提供互联网营销技术解决方案。服务范围包括移动H5开发、微信公众号、小程序、网站系统的开发与建设。
          <br>我们是时效性团队，更是您值得托付的合作伙伴。
          <br>
          <br>
          <!-- <ButtonLink 
            :linkInfo="{
              text: 'JUE.sh',
              href: ''
            }"
          /> -->
          <strong class="site-url">JUE.sh</strong>
        </span>
      </div>
    </div>
    <div class="mouse">
      <div class="roll"></div>
      <div class="rollshadow"></div>
    </div>
  </div>
</template>
<script>
import pageTitle from '@/components/pageTitle.vue'
import ButtonLink from '@/components/buttonLink.vue'
export default {
  components: {
    pageTitle,
    ButtonLink
  },
  data() {
    return {
      strings: [
        '小程序开发',
        '移动H5活动开发',
        '微信公众号开发',
        'IOS/Android APP开发',
        '网站系统建设'
      ]
    }
  }
}
</script>
<style lang="less">
.site-url{
  color: #eb4c49;
  font-size: 24px;
  font-weight: 800;
}
.typed-element {
  display: inline-block!important;
  vertical-align: bottom;
}
.typed-element .typed-cursor {
  color: #eb4c49;
}
</style>

<style lang="less" scoped>
.main {
  display: flex;
  .flex1 {
    flex: 1;
  }
  .intro {
    padding: 40px 40px 40px 100px;
    font-size: 39px;
    line-height: 1;
    span {
      display: block;
      white-space: nowrap;
      padding-bottom: 20px;
      strong {
        color: #eb4c49;
      }
    }
  }
  .intro-text {
    color: #898989;
    position: relative;
    width: 35%;
    span {
      width: 100%;
      display: block;
      position: absolute;
      bottom: 0;
      line-height: 1.6;
      padding: 40px 40px 60px;
    }
  }
}
.mouse {
  width: 26px;
  height: 40px;
  border-radius: 15px;
  border: 2px solid #000;
  position: relative;
  overflow: hidden;
  margin: 0 0 -20px 100px;
  z-index: 5;
  background: #fff;
  .roll {
    position: absolute;
    top: 8px;
    left: 50%;
    width: 4px;
    margin-left: -2px;
    height: 4px;
    border-radius: 4px;
    background: #000;
    animation: mouseScroll 0.8s cubic-bezier(0.7, 0, 0.3, 1) infinite alternate;
    z-index: 2;
  }
  .rollshadow {
    position: absolute;
    top: 8px;
    left: 50%;
    width: 4px;
    margin-left: -2px;
    height: 4px;
    background: #eb4c49;
    border-radius: 4px;
    animation: mouseScroll 0.8s cubic-bezier(0.7, 0, 0.3, 1) infinite alternate;
    -webkit-animation-delay: 80ms;
    animation-delay: 80ms;
    z-index: 1;
  }
}
@-webkit-keyframes mouseScroll {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }

  100% {
    -webkit-transform: translateY(14px);
    transform: translateY(14px);
  }
}

@keyframes mouseScroll {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }

  100% {
    -webkit-transform: translateY(14px);
    transform: translateY(14px);
  }
}

//ipad pro
@media only screen and (max-width: 1024px) {
  .main {
    .intro {
      font-size: 30px;
    }
    .intro-text {
      span {
        font-size: 13px;
      }
    }
  }
}

//ipad
@media only screen and (max-width: 768px) {
  .main {
    .intro {
      font-size: 21px;
      padding: 20px 20px 20px 50px; 
    }
    .intro-text{
      span{
        padding: 20px;
      }
    }
  }
}

//iphone
@media only screen and (max-width: 414px) {
  .main{
    flex-direction: column;
    padding-top: 30px;
    .intro{
      padding: 10px 0;
      font-size: 16px;
      span{
        padding-bottom: 10px;
      }
    }
    .intro-text{
      width: 100%;
      span{
        padding: 10px 0;
        position: relative;
      }
    }
  }
  .mouse{
    margin-left: calc(50% - 13px);
  }
}
</style>

