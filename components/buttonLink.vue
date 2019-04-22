<template>
  <a :href="linkInfo.href" class="link">
    <span>{{linkInfo.text}}</span>
    <span>{{linkInfo.text}}</span>
  </a>
</template>
<script>
export default {
  props: {
    linkInfo: Object
  }
}
</script>
<style lang="less" scoped>
a.link {
  display: inline-block;
  position: relative;
  color: #eb4c49;
  text-decoration: none;
  font-size: 24px;
  font-weight: 800;
  white-space: nowrap;
  padding-bottom: 5px;
  overflow: hidden;
  span {
    display: inline-block;
    position: relative;
    transition: opacity 0.4s cubic-bezier(0.7, 0, 0.3, 1),
      -webkit-transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
    transition: transform 0.4s cubic-bezier(0.7, 0, 0.3, 1),
      opacity 0.4s cubic-bezier(0.7, 0, 0.3, 1);
    transition: transform 0.4s cubic-bezier(0.7, 0, 0.3, 1),
      opacity 0.4s cubic-bezier(0.7, 0, 0.3, 1),
      -webkit-transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
  }
  span + span {
    position: absolute;
    top: 0;
    right: 0;
    overflow: hidden;
    -webkit-transform: translateY(100%);
    transform: translateY(100%);
    color: #121212;
    opacity: 0;
  }

  &:before {
    display: inline-block;
    position: relative;
    content: '+ ';
    transition: all 0.4s cubic-bezier(0.7, 0, 0.3, 1);
    transform-origin: 50% 50%;
  }
  &:after {
    content: '';
    display: block;
    position: absolute;
    bottom: 0;
    left: 17px;
    right: 0;
    height: 3px;
    background: #eb4c49;
    transition: transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
    transition: transform 0.4s cubic-bezier(0.7, 0, 0.3, 1),
      -webkit-transform 0.4s cubic-bezier(0.7, 0, 0.3, 1);
  }
  &:hover {
    span {
      transform: translateY(-100%);
    }
    span + span {
      opacity: 1;
      transform: translateY(0);
    }
    &:before {
      transform: rotate(90deg);
      transition: all 0.4s cubic-bezier(0.7, 0, 0.3, 1);
      color: #121212;
    }
    &:after{
      transform: translateY(20px);
    }
  }
}
@media only screen and (max-width: 1024px) {
  a.link{
    font-size: 20px;
  }
}
@media only screen and (max-width: 768px) {
  a.link{
    font-size: 16px;
  }
}
</style>


