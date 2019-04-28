<template>
  <div class="wrapper-case">
    <div class="case-blank"></div>
    <div class="container-case">
      <div class="case-title">开发案例</div>
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
    <div class="list">
      <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper">
          <div :key="index" class="swiper-slide" v-for="(bannerCase,index) in bannerCases">
            <a class="case-preview" href="javascript:;">
              <div class="case-visuel" style="background-color:#bbd39e">
                <div :style="{backgroundImage:`url(${bannerCase.url})`}" class="visuel"></div>
              </div>
              <div class="inner">
                <div class="title">{{bannerCase.title}}</div>
                <div class="desc">{{bannerCase.desc}}</div>
              </div>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import pageTitle from '@/components/pageTitle.vue'
export default {
  components: {
    pageTitle
  },
  beforeMount() {
    if (document.body.clientWidth <= 414) {
      this.swiperOption.slidesPerView = 1
    } else {
      this.swiperOption.slidesPerView = 4
    }
  },
  data() {
    return {
      clientWidth: null,
      bannerCases: [
        {
          title: 'BIMGO',
          desc: '基于BIM的施工管理、运营平台',
          url: 'https://filecdn.jue.sh/1556002545584.png'
        },
        {
          title: '微商',
          desc: '电商类小程序',
          url: 'https://filecdn.jue.sh/1556001859475.png'
        },
        {
          title: '微信公众号',
          desc: '在线互联网社区',
          url: 'https://filecdn.jue.sh/1556002032220.png'
        },
        {
          title: 'PC网站',
          desc: '后台统计系统',
          url: 'https://filecdn.jue.sh/1556002428838.png'
        }
      ],
      swiperOption: {
        slidesPerView: 4,
        centeredSlides: true,
        paginationClickable: true,
        spaceBetween: 30,
        nextButton: '.sBtn-next',
        prevButton: '.sBtn-prev'
      }
    }
  }
}
</script>
<style lang="less" scoped>
.wrapper-case {
  padding-top: 200px;
  padding-bottom: 200px;
  position: relative;
  .case-blank {
    height: 268px;
    background: #efefef;
    width: 35%;
    position: absolute;
    top: 0;
    left: 0;
  }
  .container-case {
    display: flex;
    .case-title {
      font-size: 40px;
      padding: 40px 40px 40px 100px;
      flex: 1;
    }
    .sBtns {
      width: 120px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      .sBtn-prev,
      .sBtn-next {
        cursor: pointer;
        border-radius: 50%;
        background: #eb4c49;
        height: 50px;
        width: 50px;
        display: flex;
        align-items: center;
        justify-content: center;
        .arrow {
          svg {
            width: 30px;
          }
        }
        &.swiper-button-disabled {
          opacity: 0.4;
        }
      }
    }
  }
}
.case-preview {
  display: block;
  text-decoration: none;
  color: #121212;
  .inner {
    .title {
      font-size: 21px;
      font-weight: bold;
      padding: 20px 0 10px;
    }
    .desc {
      color: #898989;
      line-height: 1.4;
    }
  }
  .case-visuel {
    overflow: hidden;
    position: relative;
    transform-origin: center center;
    transition: all 0.4s cubic-bezier(0.215, 0.61, 0.355, 1);
    &:before {
      content: '';
      display: block;
      width: 100%;
      padding-top: 60%;
      background: #efefef;
      position: relative;
      z-index: 0;
    }
    .visuel {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-size: 100% 100%;
      background-position: center center;
      background-repeat: no-repeat;
      z-index: 1;
      transform: scale(1.1);
      transition: transform 1.2s cubic-bezier(0.215, 0.61, 0.355, 1);
      transition: transform 1.2s cubic-bezier(0.215, 0.61, 0.355, 1),
        -webkit-transform 1.2s cubic-bezier(0.215, 0.61, 0.355, 1);
    }
  }
  &:hover {
    .case-visuel {
      transform: scale(0.95) !important;
    }
  }
}

.my-swiper {
  width: 100%;
  height: 300px;
  margin: 20px auto;
}

@media only screen and (max-width: 768px) {
  .wrapper-case {
    .case-title {
      padding: 20px 20px 20px 50px;
    }
  }
}
@media only screen and (max-width: 414px) {
  .wrapper-case {
    padding-top: 0;
    .case-blank{
      height: 34px;
    }
    .container-case {
      .case-title {
        font-size: 20px;
        padding: 20px 0;
      }
      .sBtns {
        width: 70px;
        .sBtn-prev,
        .sBtn-next {
          width: 30px;
          height: 30px;
          .arrow {
            svg {
              width: 20px;
            }
          }
        }
      }
    }
  }
  .case-preview {
    .inner {
      .title {
        font-size: 16px;
        font-weight: bold;
        padding: 10px 0 5px;
      }
      .desc {
        color: #898989;
        font-size: 12px;
        line-height: 1.4;
      }
    }
  }
  .list {
    padding: 20px;
  }
}
</style>


