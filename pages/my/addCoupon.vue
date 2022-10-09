<template>
  <view>
    <!-- start add-coupon -->
    <view class="add-coupon">
      <!-- start column -->
      <view class="column">
        <view class="column-name">优惠券类型</view>
        <view class="column-content">
          <CouponCard scene="addShow" :coupon="couponInfo" />
        </view>
      </view>
      <!-- end column -->
      <!-- start column-hint -->
      <view class="column-hint">平台使用规则：必须到店消费</view>
      <!-- end column-hint -->
      <view style="padding: 0 16rpx">
        <!-- start shop-card -->
        <view class="shop-card">
          <view class="shop-card-name">门店使用规则</view>
          <view class="shop-card-textarea">
            <textarea placeholder="请输入门店使用规则"></textarea>
            <view class="textarea-count">28/100</view>
          </view>
        </view>
        <!-- end shop-card -->
      </view>
    </view>
    <!-- end add-coupon -->
    <!-- start operation -->
    <view class="operation">
      <view class="add-btn">添加优惠券</view>
    </view>
    <!-- end operation -->
  </view>
</template>

<script>
import CouponCard from "@/components/couponCard/couponCard.vue";
export default {
  data() {
    return {
      // 优惠劵信息
      couponInfo: {
        title: "洁牙卡一次",
        type: 0,
      },
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
  components: { CouponCard },
};
</script>

<style lang="less" scoped>
.add-coupon {
  padding: 0 14rpx;
  .column {
    .column-name {
      padding: 30rpx 0;
      padding-left: 16rpx;
      font-size: 28rpx;
      font-weight: 600;
      color: #333333;
    }
  }
  .column-hint {
    padding: 30rpx 0;
    padding-left: 16rpx;
    font-size: 24rpx;
    font-weight: 400;
    color: #333333;
  }
  .shop-card {
    width: 100%;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 26rpx 50rpx 40rpx 50rpx;
    .shop-card-name {
      font-size: 28rpx;
      font-weight: 500;
      color: #333333;
    }
    .shop-card-textarea {
      margin-top: 36rpx;
      width: 100%;
      height: 190rpx;
      background: #f5f5f5;
      border-radius: 16rpx;
      padding: 8rpx 12rpx;
      box-sizing: border-box;
      position: relative;
      textarea {
        width: 100%;
        height: 140rpx;
        font-size: 24rpx;
        font-weight: 400;
        color: #333333;
        line-height: 48rpx;
      }
      .textarea-count {
        position: absolute;
        right: 28rpx;
        bottom: 14rpx;
        font-size: 24rpx;
        font-weight: 400;
        color: #999999;
      }
    }
  }
}

.operation {
  position: fixed;
  bottom: 0;
  width: 100%;
  padding: 20rpx 60rpx;
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  box-sizing: border-box;
  .add-btn {
    padding: 20rpx 0;
    background: #c78125;
    border-radius: 16rpx;
    font-size: 32rpx;
    font-weight: 600;
    color: #ffffff;
    text-align: center;
  }
}
</style>
