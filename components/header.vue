<template>
  <div class="wrapper-header">
    <header class="container-header"></header>
    <div :class="isFixed ? 'fixed' : ''" class="menu">
      <a class="logo" href="https://jue.sh">
        <svg
          height="100%"
          preserveAspectRatio="xMidYMid meet"
          version="1.0"
          viewBox="0 0 800.000000 800.000000"
          width="100%"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g
            fill="#eb4c49"
            stroke="none"
            transform="translate(0.000000,800.000000) scale(0.100000,-0.100000)"
          >
            <path
              d="M0 4000 l0 -4000 4000 0 4000 0 0 4000 0 4000 -4000 0 -4000 0 0 -4000z m2418 1214 c12 -8 26 -24 32 -34 14 -26 13 -1385 0 -1589 -22 -327 -112 -514 -310 -646 -137 -91 -272 -138 -455 -156 -144 -15 -209 -3 -264 49 -47 45 -55 83 -50 239 4 96 7 113 31 154 31 53 55 65 148 74 139 13 229 63 286 161 53 90 56 135 60 944 3 410 7 755 9 767 10 46 43 52 275 53 179 0 219 -3 238 -16z m1110 -12 c16 -16 20 -43 25 -193 4 -96 7 -291 7 -435 0 -278 8 -351 45 -425 54 -106 128 -151 261 -157 77 -4 98 -1 142 18 64 28 103 70 133 147 23 57 23 65 26 523 2 256 6 475 8 487 10 46 47 53 278 53 197 0 217 -2 238 -19 l24 -19 0 -539 c0 -583 -1 -599 -58 -755 -75 -207 -246 -356 -482 -420 -111 -30 -442 -33 -550 -5 -226 60 -410 206 -506 403 -82 169 -82 173 -89 762 -3 287 -2 534 2 549 4 14 13 30 20 34 7 5 113 9 236 9 202 0 224 -2 240 -18z m3063 -21 l29 -29 0 -160 0 -160 -31 -31 -31 -31 -389 0 -389 0 0 -100 0 -100 373 0 373 0 30 -31 c29 -30 29 -31 32 -171 4 -152 -3 -185 -46 -218 -24 -19 -42 -20 -393 -20 l-369 0 0 -110 0 -110 391 0 391 0 29 -29 29 -29 0 -160 c0 -181 -7 -202 -78 -222 -55 -15 -1196 -13 -1241 3 -19 7 -42 23 -53 37 -17 24 -18 64 -18 828 0 532 3 809 10 822 28 52 6 50 688 50 l634 0 29 -29z"
            ></path>
          </g>
        </svg>
      </a>
      <div class="flex-1"></div>
      <div class="toggle-menu">
        <span class="toggle-text" :class="toggleClose ? 'txt-close' : ''">联系我们</span>
        <div :class="toggleClose ? 'toggle-close' : ''" @click="changeMenu" class="toggle-btn">
          <span class="line line1"></span>
          <span class="line line2"></span>
          <span class="line line3"></span>
          <span class="line line4"></span>
          <span class="line line5"></span>
          <span class="line line6"></span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    toggleClose: {
      default: false
    }
  },
  data() {
    return {
      isFixed: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    changeMenu() {
      this.$emit('changeMenu')
    },
    handleScroll() {
      let scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop
      if (document.documentElement.scrollTop >= 90) {
        this.isFixed = true
      } else {
        this.isFixed = false
      }
    }
  }
}
</script>

<style lang="less" scoped>
.wrapper-header {
  position: relative;
  .container-header {
    height: 270px;
  }
}

.menu {
  display: flex;
  align-items: center;
  padding: 0 40px;
  top: 40px;
  position: absolute;
  width: 100%;
  left: 50%;
  max-width: 1440px;
  transform: translateX(-50%);
  z-index: 100;
  &.fixed {
    position: fixed;
    transition: all 0.25s linear;
    max-width: 100%;
  }
  .logo {
    display: inline-block;
    width: 50px;
    height: 50px;
    background-color: #fff;
  }
  .toggle-menu {
    display: flex;
    align-items: center;
    justify-content: center;
    .toggle-text {
      font-size: 12px;
      font-weight: bold;
      margin-right: 10px;
      &.txt-close{
        color: #fff;
      }
    }
    .toggle-btn {
      cursor: pointer;
      width: 30px;
      height: 20px;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      &:hover {
      }
      .line {
        display: block;
        height: 2px;
        width: 50%;
        position: absolute;
        background-color: rgba(18, 18, 18, 1);
        transition: All 0.25s linear;
        &.line1 {
          top: 0px;
          left: 0px;
        }
        &.line2 {
          top: 0px;
          left: 50%;
        }
        &.line3 {
          top: 9px;
          right: 50%;
        }
        &.line4 {
          top: 9px;
          left: 50%;
        }
        &.line5 {
          top: 18px;
          left: 0px;
        }
        &.line6 {
          top: 18px;
          left: 50%;
        }
      }
      &.toggle-close {
        .line{
          background-color: #fff;
        }
        .line1 {
          transform: translate(3px, 4px) rotate(45deg);
        }
        .line2 {
          transform: translate(-3px, 4px) rotate(-45deg);
        }
        .line3 {
          width: 0;
        }
        .line4 {
          width: 0;
        }
        .line5 {
          transform: translate(3px, -5px) rotate(-45deg);
        }
        .line6 {
          transform: translate(-3px, -5px) rotate(45deg);
        }
      }
    }
  }
}
@media only screen and (max-width: 414px) {
  .menu{
    top: 0px;
    padding: 10px 40px;
    background-color: #fff;
    border-bottom: 1px #f7f7f7 solid;
    .toggle-menu{
      .toggle-text{
        &.txt-close{
          color: #121212;
        }
      }
      .toggle-btn.toggle-close{
        .line{
          background-color: #121212;
        }
      }
    }
  }
}
</style>

