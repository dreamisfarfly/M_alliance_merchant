<template>
  <!-- start coupon-card -->
  <view class="coupon-card">
    <!-- start coupon-type-card -->
    <view class="coupon-type-card">
      <img
        v-if="coupon.type == 0"
        class="coupon-type-icons"
        src="/static/images/discount-coupon-magcard.png"
      />
      <img
        v-if="coupon.type == 1"
        class="coupon-type-icons"
        src="/static/images/discount-coupon-consumer-voucher.png"
      />
      <img
        v-if="coupon.type == 2"
        class="coupon-type-icons"
        src="/static/images/discount-coupon-cash-coupon.png"
      />
    </view>
    <!-- end coupon-type-card -->
    <!-- start coupon-info-card -->
    <view class="coupon-info-card">
      <!-- start coupon-info-card-header -->
      <view class="coupon-info-card-header">
        <view class="coupon-info-card-header-name">{{ coupon.title }}</view>
        <view class="addition-btn" v-if="scene == 'listShow'">下架</view>
        <view class="addition-btn" v-if="scene == 'listAdd'">添加</view>
      </view>
      <!-- end coupon-info-card-header -->
      <!-- start coupon-info-card-value -->
      <view class="coupon-info-card-value">
        <template v-if="coupon.type == 0">价值 188元</template>
        <template v-if="coupon.type == 1">满100减10元现金券</template>
        <template v-if="coupon.type == 2">现金直接抵扣</template>
      </view>
      <!-- end coupon-info-card-value -->
      <!-- start coupon-info-card-separator -->
      <view class="coupon-info-card-separator"></view>
      <!-- end coupon-info-card-separator -->
      <!-- start coupon-info-card-expiration-time -->
      <view class="coupon-info-card-expiration-time">
        <text>领取后30天有效</text>
        <text v-if="scene == 'listShow'">10家门店适用></text>
        <text v-if="scene == 'addShow'" class="coupon-price"
          >￥5.00/100积分</text
        >
      </view>
      <!-- end coupon-info-card-expiration-time -->
    </view>
    <!-- end coupon-info-card -->
  </view>
  <!-- end coupon-card -->
</template>

<script>
export default {
  props: {
    // 场景
    scene: {
      typeof: String,
      default: "listShow", //默认优惠劵列表
    },
    // 优惠劵
    coupon: {
      typeof: Object,
      default: function () {
        return {};
      },
    },
  },
};
</script>

<style lang="less" scoped>
.coupon-card {
  width: 100%;
  height: 240rpx;
  background: url("/static/images/discount-coupon-bak.png");
  background-size: 100% 100%;
  display: flex;
  .coupon-type-card {
    width: 152rpx;
    height: 100%;
    padding-left: 30rpx;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    .coupon-type-icon {
      width: 122rpx;
      height: 158rpx;
    }
    .coupon-type-icons {
      width: 98rpx;
      height: 106rpx;
    }
  }
  .coupon-info-card {
    flex: 1;
    padding: 6rpx 46rpx 18rpx 16rpx;
    box-sizing: border-box;
    .coupon-info-card-header {
      padding-top: 24rpx;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-sizing: border-box;
      .coupon-info-card-header-name {
        font-size: 32rpx;
        font-weight: 500;
        color: #333333;
      }
      .addition-btn {
        width: 120rpx;
        height: 50rpx;
        border-radius: 8rpx;
        border: 2rpx solid #c78125;
        text-align: center;
        line-height: 50rpx;
        box-sizing: border-box;
        font-size: 24rpx;
        font-weight: 500;
        color: #c78125;
      }
    }
  }
  .coupon-info-card-value {
    margin-top: 16rpx;
    font-size: 24rpx;
    font-weight: 400;
    color: #999999;
  }
  .coupon-info-card-separator {
    margin-top: 22rpx;
    width: 100%;
    height: 2rpx;
    background: #f0f0f0;
  }
  .coupon-info-card-expiration-time {
    margin-top: 18rpx;
    font-size: 20rpx;
    font-weight: 400;
    color: #999999;
    display: flex;
    justify-content: space-between;
  }
}

.coupon-price {
  font-size: 28rpx;
  font-weight: 500;
  color: #c78125;
}
</style>
