<template>
  <!-- start coupon-cancellation -->
  <view class="coupon-cancellation">
    <!-- start coupon-cancellation-header -->
    <view class="coupon-cancellation-header">
      <!-- start 导航栏 -->
      <u-navbar
        title="优惠券核销"
        :is-back="false"
        title-color="#FFFFFF"
        title-size="36"
        :border-bottom="false"
      ></u-navbar>
      <!-- end 导航栏 -->
      <!-- start coupon-cancellation-header-content -->
      <view class="coupon-cancellation-header-content">
        <CouponCancellationCard></CouponCancellationCard>
        <!-- start member-information-card -->
        <view class="member-information-card">
          <view class="member-information-name">会员信息</view>
          <view class="justify">
            <view class="member-name">
              张三
              <view class="member-label">年卡会员</view>
            </view>
            <view class="member-info-font"
              >女<text style="margin-left: 42rpx">15699990000</text></view
            >
          </view>
          <view class="member-info-font" style="margin-top: 10rpx"
            >有效期至：2022-12-12</view
          >
        </view>
        <!-- end member-information-card -->
        <!-- start btn-group -->
        <view class="btn-group">
          <view class="btn return">返回</view>
          <view class="btn verification">核销</view>
        </view>
        <!-- end btn-group -->
      </view>
      <!-- end coupon-cancellation-header-content -->
    </view>
    <!-- end coupon-cancellation-header -->
    <!-- start record -->
    <view class="record">
      <view class="record-title">核销记录</view>
      <view class="record-content">
        <CouponCancellationCard
          scene="record"
          v-for="(item, key) in 6"
          :key="key"
          style="margin-bottom: 20rpx"
        ></CouponCancellationCard>
      </view>
    </view>
    <!-- end record -->
  </view>
  <!-- end coupon-cancellation -->
</template>

<script>
import CouponCancellationCard from "@/components/couponCancellationCard/couponCancellationCard.vue";
export default {
  data() {
    return {};
  },
  components: { CouponCancellationCard },
};
</script>

<style lang="less" scoped>
.coupon-cancellation {
  .coupon-cancellation-header {
    padding-bottom: 30rpx;
    width: 100%;
    background: linear-gradient(270deg, #c9a88b 0%, #996f52 100%);
    .coupon-cancellation-header-content {
      padding: 0 30rpx;
      margin-top: 20rpx;
      box-sizing: border-box;
      .member-information-card {
        padding: 16rpx 26rpx 36rpx 30rpx;
        border-radius: 10rpx;
        margin-top: 30rpx;
        box-sizing: border-box;
        background: rgba(255, 255, 255, 0.1);
        box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
        border: 2rpx solid;
        border-image: linear-gradient(
            180deg,
            rgba(255, 255, 255, 1),
            rgba(255, 255, 255, 0)
          )
          1 1;
        .member-information-name {
          font-size: 24rpx;
          font-weight: 400;
          color: #ffffff;
        }
        .justify {
          margin-top: 24rpx;
          display: flex;
          align-items: center;
          justify-content: space-between;
        }
        .member-name {
          display: flex;
          font-size: 24rpx;
          font-weight: 500;
          color: #ffffff;
        }
        .member-info-font {
          font-size: 24rpx;
          font-weight: 400;
          color: #ffffff;
        }
      }
      .btn-group {
        display: flex;
        justify-content: space-between;
        margin-top: 34rpx;
        .btn {
          width: 300rpx;
          height: 72rpx;
          border-radius: 16rpx;
          text-align: center;
          line-height: 72rpx;
          font-size: 32rpx;
          font-weight: 600;
        }
        .return {
          border: 2rpx solid #ffffff;
          color: #ffffff;
        }
        .verification {
          color: #c78125;
          background: #ffffff;
        }
      }
    }
  }
}

.record {
  margin-top: 36rpx;
  padding: 0 30rpx;
  .record-title {
    font-size: 28rx;
    font-weight: 600;
    color: #333333;
  }
  .record-content {
    margin-top: 18rpx;
  }
}

.member-label {
  margin-left: 26rpx;
  padding: 2rpx 14rpx 2rpx 18rpx;
  background: #528a13;
  border-radius: 4rpx;
  font-size: 20rpx;
  font-weight: 500;
  color: #ffffff;
}
</style>
