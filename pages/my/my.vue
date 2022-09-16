<template>
  <!-- start 我的 -->
  <view class="my"></view>
  <!-- end 我的 -->
</template>

<script>
export default {
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
};
</script>

<style scoped lang="scss">
.my {
}
</style>
