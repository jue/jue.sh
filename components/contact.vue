<template>
  <div class="wrapper-contact">
    <div class="container-contact">
      <div class="page-title">联系</div>
      <div class="contact-main">
        <div class="contact">
          <p>
            我们提供专业技术开发、服务维护
            <br>很期待与您一起合作！
          </p>
          <a @click="changeMenu" class="link" href="javascript:;">点击联系我们</a>
        </div>
        <div class="info">
          <div class="flex1"></div>
          <div class="socials">
            <a class="tel" data-tooltip="电话: 17187488188" href="tel:+8617187488188">
              <svg
                version="1.1"
                viewBox="0 0 1024 1024"
                xmlns="http://www.w3.org/2000/svg"
                xmlns:xlink="http://www.w3.org/1999/xlink"
              >
                <path
                  d="M508.84 650c-49-39.91-105.49-93.6-154.44-154.16-34.34-42.45-64.71-87-33.35-118.37L100.94 158C68.86 198-2.23 388.39 302.47 700.13c321 328.52 528.09 258.24 563.73 221.2L651.61 707c-30 29.93-68.64 3.32-142.77-57z m434.82 146.78v-0.2s-167.45-166.92-167.55-167a33.75 33.75 0 0 0-47.62 0.07l-60.69 60.74L883 905.29s60.76-60.53 60.7-60.6l0.16-0.13c13.9-13.91 12.48-35.07-0.16-47.78zM398.41 300.31v-0.17a33.57 33.57 0 0 0 0-47.69v-0.23L226.05 80.46a33.67 33.67 0 0 0-47.65 0l-60.69 60.79 219.93 219.61s60.77-60.45 60.77-60.55z"
                ></path>
              </svg>
            </a>
            <a class="wechat" href="javascript:;">
              <svg
                version="1.1"
                viewBox="0 0 1024 1024"
                xmlns="http://www.w3.org/2000/svg"
                xmlns:xlink="http://www.w3.org/1999/xlink"
              >
                <path
                  d="M1010.8 628c0-141.2-141.3-256.2-299.9-256.2-168 0-300.3 115.1-300.3 256.2 0 141.4 132.3 256.2 300.3 256.2 35.2 0 70.7-8.9 106-17.7l96.8 53-26.6-88.2c70.9-53.2 123.7-123.7 123.7-203.3zM618 588.8c-22.1 0-40-17.9-40-40s17.9-40 40-40 40 17.9 40 40c0 22-17.9 40-40 40z m194.3-0.3c-22.1 0-40-17.9-40-40s17.9-40 40-40 40 17.9 40 40-17.9 40-40 40z"
                ></path>
                <path
                  d="M366.3 106.9c-194.1 0-353.1 132.3-353.1 300.3 0 97 52.9 176.6 141.3 238.4l-35.3 106.2 123.4-61.9c44.2 8.7 79.6 17.7 123.7 17.7 11.1 0 22.1-0.5 33-1.4-6.9-23.6-10.9-48.3-10.9-74 0-154.3 132.5-279.5 300.2-279.5 11.5 0 22.8 0.8 34 2.1C692 212.6 539.9 106.9 366.3 106.9zM247.7 349.2c-26.5 0-48-21.5-48-48s21.5-48 48-48 48 21.5 48 48-21.5 48-48 48z m246.6 0c-26.5 0-48-21.5-48-48s21.5-48 48-48 48 21.5 48 48-21.5 48-48 48z"
                ></path>
              </svg>
              <span class="qrcode-box">
                <img src="https://filecdn.jue.sh/1555909757852.png">
              </span>
            </a>
            <a @click="changeMenu" class="msg" data-tooltip="给我们留言" href="javascript:;">
              <svg
                version="1.1"
                viewBox="0 0 1024 1024"
                xmlns="http://www.w3.org/2000/svg"
                xmlns:xlink="http://www.w3.org/1999/xlink"
              >
                <path
                  d="M853.333333 85.333333 170.666667 85.333333C123.733333 85.333333 85.333333 123.733333 85.333333 170.666667L85.333333 938.666667 256 768 853.333333 768C900.266667 768 938.666667 729.6 938.666667 682.666667L938.666667 170.666667C938.666667 123.306667 900.266667 85.333333 853.333333 85.333333Z"
                ></path>
              </svg>
            </a>
          </div>
          <div class="copyright">
            COPYRIGHT © 2019
            <span class="com-name">上海聚怡信息技术有限公司</span>
            <span class="studio-name">觉·上海 技术工作室</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    changeMenu() {
      this.$emit('changeMenu')
    }
  }
}
</script>

<style lang="less" scoped>
.page-title {
  position: absolute;
  top: 60px;
  left: 40px;
  transform: rotate(-90deg);
  font-weight: bold;
  color: #fff;
}
.wrapper-contact {
  background-color: #000;
  padding: 100px 0;
}
.contact-main {
  display: flex;
  .contact {
    padding: 40px 40px 40px 100px;
    color: #fff;
    font-size: 20px;
    width: 50%;
    .link {
      display: inline-block;
      margin-top: 10px;
      color: #eb4c49;
      position: relative;
      transition: color 0.4s cubic-bezier(0.7, 0, 0.3, 1);
      text-decoration: none;
      font-weight: bold;
      font-size: 30px;
      &:hover {
        color: #fff;
        &:after {
          transform: scaleX(1);
          transform-origin: left center;
        }
      }
      &:before {
        content: '';
        display: block;
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        height: 4px;
        border-radius: 3px;
        background: #eb4c49;
      }
      &:after {
        content: '';
        display: block;
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        height: 4px;
        background: #fff;
        border-radius: 3px;
        transform: scaleX(0);
        transition: -webkit-transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
        transition: transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
        transition: transform 0.4s cubic-bezier(0.7, 0, 0.3, 1),
          -webkit-transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
        transform-origin: right center;
      }
    }
  }
  .info {
    flex: 1;
    text-align: right;
    display: flex;
    flex-direction: column;
    .flex1 {
      flex: 1;
    }
    .socials {
      padding: 20px 0;
      a {
        display: inline-block;
        padding: 10px;
        border-radius: 50%;
        margin: 0 5px;
        position: relative;
        z-index: 1;
        &:hover {
          background-color: rgba(255, 255, 255, 0.5);
          svg {
            fill: #eb4c49;
          }
        }
        svg {
          width: 25px;
          fill: #fff;
        }
        &.wechat {
          &:hover {
            .qrcode-box {
              display: inline-block;
            }
          }
          .qrcode-box {
            display: none;
            position: absolute;
            bottom: calc(100% + 10px);
            position: absolute;
            border: 1px solid #ddd;
            border-radius: 2px;
            width: 120px;
            height: 120px;
            left: 50%;
            transform: translateX(-50%);
            &:after {
              background-color: #fff;
              border-bottom: 1px solid #ddd;
              border-left: 1px solid #ddd;
              bottom: -5px;
              content: '';
              height: 10px;
              position: absolute;
              left: 50%;
              transform: translateX(-50%) rotate(-45deg);
              width: 10px;
              z-index: 2;
            }
          }
        }
      }
    }

    .copyright {
      color: rgba(255, 255, 255, 0.5);
      font-size: 13px;
      .com-name {
        color: rgba(255, 255, 255, 1);
      }
      .studio-name {
        display: block;
        font-size: 12px;
        padding-top: 5px;
      }
    }
  }
}

@media only screen and (max-width: 768px) {
  .page-title {
    font-size: 12px;
    top: 30px;
  }
}

@media only screen and (max-width: 414px) {
  .page-title {
    transform: rotate(0deg);
    top: 0;
  }
  .contact-main {
    flex-direction: column;
    .contact {
      width: 100%;
      padding: 30px 20px 20px 0;
      font-size: 15px;
      .link {
        font-size: 20px;
      }
    }
    .info {
      text-align: left;
    }
  }
}
</style>
