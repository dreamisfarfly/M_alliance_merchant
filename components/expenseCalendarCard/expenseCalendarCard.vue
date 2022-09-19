<template>
  <!-- start expense-calendar-card -->
  <view class="expense-calendar-card">
    <!-- start texpense-calendar-card-genre -->
    <view class="texpense-calendar-card-genre">
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
    </view>
    <!-- end texpense-calendar-card-genre -->
    <!-- start texpense-calendar-card-info -->
    <view class="texpense-calendar-card-info">
      <!-- start card-info -->
      <view class="card-info">
        <!-- start user-info -->
        <view class="user-info">
          <view class="user-name">张三</view>
          <view class="card-group">
            <view class="user-vip-label annual-card">年卡</view>
            <view class="user-vip-label platform-members">平台会员</view>
          </view>
        </view>
        <!-- end user-info -->
        <!-- start card-phone -->
        <view class="card-phone">1568888999</view>
        <!-- end card-phone -->
      </view>
      <!-- end card-info -->
      <view class="special-offers">
        <view class="special-offers-info">优惠：412.00元</view>
        <view class="special-offers-info"
          >实际收款：<text style="color: #c78125">588.00</text>元</view
        >
      </view>
      <view style="margin-top: 16rpx" class="special-offers-info"
        >2022年9月2日17:19:47</view
      >
    </view>
    <!-- end texpense-calendar-card-info -->
  </view>
  <!-- end expense-calendar-card -->
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
.expense-calendar-card {
  width: 100%;
  height: 314rpx;
  box-sizing: border-box;
  display: flex;
  background: url("/static/images/expense-calendar-card-bak.png");
  background-size: 100% 100%;
  padding: 8rpx 16rpx 26rpx 16rpx;
  .texpense-calendar-card-genre {
    width: 140rpx;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    .coupons-type-icon {
      width: 98rpx;
      height: 98rpx;
    }
  }
  .texpense-calendar-card-info {
    flex: 1;
    padding: 30rpx 20rpx 22rpx 28rpx;
    box-sizing: border-box;
    .card-info {
      border-bottom: 2rpx dashed #e3e3e3;
      padding-bottom: 24rpx;
      .user-info {
        display: flex;
        align-items: center;
        justify-content: space-between;
        .user-name {
          font-size: 28rpx;
          font-weight: 500;
          color: #000000;
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
      }
    }
    .special-offers {
      margin-top: 20rpx;
      display: flex;
      justify-content: space-between;
    }
    .special-offers-info {
      font-size: 24rpx;
      font-weight: 400;
      color: #999999;
    }
  }
}
</style>
