<template>
  <!-- start score -->
  <view class="score">
    <img
      v-for="(item, key) in evaluationScore"
      :key="key"
      class="star-icon"
      src="/static/images/yes-star-icon.png"
    />
    <template v-if="fullStarsCount - evaluationScore > 0">
      <img
        v-for="(item, key) in fullStarsCount - evaluationScore"
        :key="key"
        class="star-icon"
        src="/static/images/not-star-icon.png"
      />
    </template>
  </view>
  <!-- end score -->
</template>

<script>
export default {
  props: {
    // 满星数量
    fullStarsCount: {
      typeof: Number,
      default: 5,
    },
    // 评分数
    evaluationScore: {
      type: Number,
      default: 0,
    },
  },
};
</script>

<style lang="less" scoped>
.score {
  display: flex;
}
.star-icon {
  width: 24rpx;
  height: 24rpx;
  margin-right: 2rpx;
}
</style>
