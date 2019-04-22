<template>
  <nuxt/>
</template>

<style>
html {
  font-family: 'Helvetica Neue', Helvetica, Arial, 'PingFang SC',
    'Microsoft Yahei', 'Wenquanyi Micro Hei', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
  transition: all 0.25s linear;
  vertical-align: middle;
}
::-webkit-scrollbar {
  display: none;
}
[class*=' container-'],
[class^='container-'] {
  position: relative;
  width: 100%;
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 40px;
}
.flex-1 {
  flex: 1;
}
img {
  max-width: 100%;
}
[data-tooltip] {
  position: relative;
  z-index: 2;
  cursor: pointer;
}

[data-tooltip]:before,
[data-tooltip]:after {
  visibility: hidden;
  -ms-filter: 'progid:DXImageTransform.Microsoft.Alpha(Opacity=0)';
  filter: progid: DXImageTransform.Microsoft.Alpha(Opacity=0);
  opacity: 0;
  pointer-events: none;
}

[data-tooltip]:before {
  position: absolute;
  bottom: calc(100% + 10px);
  left: 50%;
  transform: translateX(-50%);
  padding: 7px;
  white-space: nowrap;
  border-radius: 2px;
  background-color: #fff;
  color: #121212;
  content: attr(data-tooltip);
  text-align: center;
  font-size: 14px;
  line-height: 1.2;
}

[data-tooltip]:after {
  position: absolute;
  bottom: calc(100% + 4px);
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  border-top: 8px solid #fff;
  border-right: 8px solid transparent;
  border-left: 8px solid transparent;
  content: ' ';
  font-size: 0;
  line-height: 0;
}

[data-tooltip]:hover:before,
[data-tooltip]:hover:after {
  visibility: visible;
  filter: progid: DXImageTransform.Microsoft.Alpha(Opacity=100);
  opacity: 1;
}
</style>
