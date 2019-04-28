<template>
  <div class="wrapper-product" style="background-color: #febb12;">
    <div class="container-product">
      <div style="width: 40%;"></div>
      <img src="https://filecdn.jue.sh/1555933018611.svg">
    </div>
    <div class="sBtns-wrapper">
      <div class="flex1"></div>
      <div class="sBtns">
        <div class="sBtn-prev">
          <i class="arrow">
            <svg
              version="1.1"
              viewBox="0 0 1024 1024"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <path
                d="M685.76 830.24l-11.312 11.328a16 16 0 0 1-22.64 0L340.688 530.448a16 16 0 0 1 0-22.64l311.12-311.12a16 16 0 0 1 22.64 0l11.312 11.312a16 16 0 0 1 0 22.624L397.248 519.12 685.76 807.632a16 16 0 0 1 0 22.624z"
                fill="#ffffff"
                p-id="1911"
              ></path>
            </svg>
          </i>
        </div>
        <div class="sBtn-next">
          <i class="arrow">
            <svg
              version="1.1"
              viewBox="0 0 1024 1024"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <path
                d="M340.688 830.24l11.312 11.328a16 16 0 0 0 22.624 0L685.76 530.448a16 16 0 0 0 0-22.64L374.624 196.688a16 16 0 0 0-22.624 0l-11.312 11.312a16 16 0 0 0 0 22.624l288.496 288.496-288.496 288.512a16 16 0 0 0 0 22.624z"
                fill="#ffffff"
                p-id="1540"
              ></path>
            </svg>
          </i>
        </div>
      </div>
    </div>
    <div class="container-content">
      <pageTitle :pTitle="'产品'"></pageTitle>
      <div class="content">
        <span class="title">
          BIMGO
          <br>基于 BIM+ 工程建设管理平台
        </span>
        <div class="desc">
          快速上手的BIM应用工具，高性价比的工程管理工具，开放共享的数据可视化工具。
        </div>
        <ButtonLink :linkInfo="linkInfo"/>
      </div>
    </div>
  </div>
</template>
<script>
import ButtonLink from '@/components/buttonLink.vue'
import pageTitle from '@/components/pageTitle.vue'
export default {
  components: {
    ButtonLink,
    pageTitle
  },
  data() {
    return {
      linkInfo: {
        text: '访问官网',
        href: 'https://www.bimgosoft.com'
      }
    }
  }
}
</script>

<style lang="less" scoped>
.flex1 {
  flex: 1;
}
.wrapper-product {
  z-index: 1;
  height: 100vw;
  max-height: 700px;
  position: relative;
  background-color: #febb12;
  .container-product {
    display: flex;
    height: 100%;
    img{
      width: 800px;
    }
  }
  .sBtns-wrapper {
    position: absolute;
    bottom: 0;
    width: calc(50% + 160px);
    background-color: #fff;
    display: flex;
    .sBtns {
      background: #121212;
      display: flex;
      width: 160px;
      z-index: 5;
      cursor: pointer;
      .sBtn-prev,
      .sBtn-next {
        flex: 1;
        height: 80px;
        display: flex;
        align-items: center;
        justify-content: center;
        svg {
          transition: width 0.25s linear;
          width: 20px;
        }
        &:hover {
          svg {
            width: 40px;
          }
        }
      }
    }
  }
  .container-content {
    .content {
      width: 50%;
      margin-top: -218px;
      position: relative;
      z-index: 2;
      padding: 40px 150px 40px 100px;
      .title {
        font-size: 40px;
        line-height: 1.2;
        font-weight: bold;
      }
      .desc {
        color: #898989;
        padding: 20px 0 40px;
        line-height: 1.5;
      }
    }
  }
}

//ipad pro
@media only screen and (max-width: 1024px) {
  .wrapper-product {
    .container-content {
      .content {
        padding-right: 40px;
      }
    }
  }
}

//ipad
@media only screen and (max-width: 768px) {
  .wrapper-product {
    .container-content {
      .content {
        padding: 20px 20px 20px 50px;
        margin-top: -195px;
      }
    }
  }
}

//iphone
@media only screen and (max-width: 414px) {
  .wrapper-product {
    .container-content {
      .content {
        padding: 30px 0 10px;
        margin-top: -137px;
        .title {
          font-size: 20px;
        }
        .desc {
          font-size: 13px;
        }
      }
    }
    .sBtns-wrapper {
      width: 100%;
      .sBtns {
        width: 120px;
        .sBtn-prev,
        .sBtn-next {
          height: 60px;
        }
      }
    }
  }
}
</style>

