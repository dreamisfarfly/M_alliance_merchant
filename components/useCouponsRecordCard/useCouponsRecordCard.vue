<template>
  <!-- start use-coupons-record-card -->
  <view class="use-coupons-record-card">
    <!-- start use-coupons-record-card-genre -->
    <view class="use-coupons-record-card-genre">
      <img
        v-if="coupons.type == 0"
        class="coupons-type-icon"
        src="/static/images/discount-coupon-magcard.png"
      />
      <img
        v-if="coupons.type == 1"
        class="coupons-type-icon"
        src="/static/images/discount-coupon-consumer-voucher.png"
      />
      <img
        v-if="coupons.type == 2"
        class="coupons-type-icon"
        src="/static/images/discount-coupon-cash-coupon.png"
      />
      <view class="coupons-title" style="margin-top: 14rpx">10元消费券</view>
      <view class="coupons-title">满100减10元现金券</view>
    </view>
    <!-- end use-coupons-record-card-genre -->
    <!-- start use-coupons-record-card-info -->
    <view class="use-coupons-record-card-info">
      <view class="user-info">
        <view class="user-name">张三</view>
        <view class="card-group">
          <view class="user-vip-label annual-card">年卡</view>
          <view class="user-vip-label platform-members">平台会员</view>
        </view>
      </view>
      <view class="card-phone">1568888999</view>
      <view class="market">
        <view class="market-name">核销人：张三备份</view>
        <view class="market-at">2022-8-29 16:32:24</view>
      </view>
    </view>
    <!-- end use-coupons-record-card-info -->
  </view>
  <!-- end use-coupons-record-card -->
</template>

<script>
export default {
  props: {
    // 优惠劵信息
    coupons: {
      typeof: Object,
      default: function () {
        return {};
      },
    },
  },
};
</script>

<style lang="less" scoped>
.use-coupons-record-card {
  width: 100%;
  height: 240rpx;
  background: url("/static/images/use-coupons-record-bak.png");
  background-size: 100% 100%;
  padding: 8rpx 16rpx 20rpx 16rpx;
  box-sizing: border-box;
  display: flex;
  .use-coupons-record-card-genre {
    width: 224rpx;
    height: 206rpx;
    display: flex;
    align-items: center;
    flex-flow: column;
    .coupons-type-icon {
      margin-top: 22rpx;
      width: 98rpx;
      height: 98rpx;
    }
    .coupons-title {
      font-size: 20rpx;
      font-weight: 500;
      color: #999999;
      line-height: 28rpx;
    }
  }
  .use-coupons-record-card-info {
    flex: 1;
    padding: 32rpx 38rpx 20rpx 28rpx;
    box-sizing: border-box;
    .user-info {
      display: flex;
      align-items: center;
      justify-content: space-between;

      .user-name {
        font-size: 28rpx;
        font-weight: 500;
        color: #000000;
        line-height: 40rpx;
      }
      .card-group {
        display: flex;
        .user-vip-label {
          margin-left: 10rpx;
          padding: 2rpx 14rpx 2rpx 16rpx;
          border-radius: 4rpx;
          font-size: 20rpx;
          font-weight: 600;
        }
        .annual-card {
          background: rgba(245, 154, 35, 0.1);
          border: 2rpx solid #c78125;
          color: #c78125;
        }
        .platform-members {
          background: rgba(82, 138, 19, 0.1);
          border: 2rpx solid #3c8d00;
          color: #3c8d00;
        }
      }
    }
    .card-phone {
      margin-top: 10rpx;
      font-size: 28rpx;
      font-weight: 400;
      color: #000000;
      line-height: 40rpx;
    }
    .market {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-top: 32rpx;
      line-height: 34rpx;
      .market-name {
        font-size: 24rpx;
        font-weight: 400;
        color: #999999;
      }
      .market-at {
        font-size: 24rpx;
        font-weight: 400;
        color: #999999;
      }
    }
  }
}
</style>
