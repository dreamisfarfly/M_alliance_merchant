<template>
  <!-- start coupon-cancellation-card -->
  <view class="coupon-cancellation-card">
    <!-- start coupon-cancellation-card-header -->
    <view class="coupon-cancellation-card-header">
      <!-- start coupon-type -->
      <view class="coupon-type">
        <img
          class="coupon-icon"
          src="/static/images/discount-coupon-magcard.png"
        />
      </view>
      <!-- end coupon-type -->
      <view class="coupon-info">
        <view
          :class="[
            scene == 'header' ? 'coupon-info-name-header' : '',
            scene == 'record' ? 'coupon-info-name-record' : '',
          ]"
          >券码：545613213</view
        >
        <view
          class="coupon-info-subheading"
          :style="[{ fontSize: scene == 'header' ? '24rpx' : '32rpx' }]"
          >洁牙卡一次</view
        >
        <view class="hint" style="margin-top: 10rpx"
          >有效期至 2022年6月27日</view
        >
      </view>
    </view>
    <!-- end coupon-cancellation-card-header -->
    <!-- start coupon-cancellation-card-footer -->
    <view class="coupon-cancellation-card-footer">
      <template v-if="scene == 'header'">
        <view class="hint">平台规则：必须到店使用</view>
        <view class="hint">门店规则：周六、周日不可用</view>
      </template>
      <template v-if="scene == 'record'">
        <view class="hint">核销门店：巢爷老味（洞井路店）</view>
        <view class="justify-align" style="margin-top: 14rpx">
          <view class="hint">核销人：张三</view>
          <view class="hint">核销时间：2022年5月27日16:18</view>
        </view>
      </template>
    </view>
    <!-- end coupon-cancellation-card-footer -->
  </view>
  <!-- end coupon-cancellation-card -->
</template>

<script>
export default {
  props: {
    // 场景
    scene: {
      typeof: String,
      default: "header",
    },
  },
};
</script>

<style lang="less" scoped>
.coupon-cancellation-card {
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  border-radius: 10rpx;
  .coupon-cancellation-card-header {
    padding: 26rpx 0 20rpx 0;
    border-bottom: 2rpx dashed #e3e3e3;
    display: flex;
    .coupon-type {
      width: 134rpx;
      border-right: 2rpx dashed #e3e3e3;
      padding-top: 26rpx;
      padding-bottom: 30rpx;
      display: flex;
      justify-content: center;
      .coupon-icon {
        width: 98rpx;
        height: 98rpx;
      }
    }
    .coupon-info {
      flex: 1;
      padding-left: 16rpx;
      .coupon-info-name-header {
        font-size: 40rpx;
        font-weight: 500;
        color: #c78125;
      }
      .coupon-info-name-record {
        font-size: 28rpx;
        font-weight: 500;
        color: #c7c7c7;
      }
      .coupon-info-subheading {
        margin-top: 20rpx;
        font-weight: 500;
        color: #333333;
      }
      .coupon-info-at {
        margin-top: 10rpx;
        font-size: 20rpx;
        font-weight: 400;
        color: #999999;
      }
    }
  }
  .coupon-cancellation-card-footer {
    padding: 24rpx 22rpx;
  }
}

.hint {
  font-size: 20rpx;
  font-weight: 400;
  color: #999999;
}

.justify-align {
  display: flex;
  justify-content: space-between;
}
</style>
