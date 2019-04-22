<template>
  <div class="page-title">
    {{pTitle}}
  </div>
</template>
<script>
export default {
  props: ['pTitle']
}
</script>
<style lang="less" scoped>
.page-title{
  position: absolute;
  top: 60px;
  left: 40px;
  transform: rotate(-90deg);
  font-weight: bold;
}
@media only screen and (max-width: 768px) {
  .page-title{
    font-size: 12px;
    top: 30px;
  }
}

@media only screen and (max-width: 414px) {
  .page-title{
    transform: rotate(0deg);
    top: 0;
  }
}
</style>


