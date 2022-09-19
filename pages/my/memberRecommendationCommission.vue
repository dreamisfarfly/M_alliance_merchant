<template>
  <!-- start member-recommendation-commission -->
  <view class="member-recommendation-commission">
    <!-- start commission-card -->
    <view class="commission-card">
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-name">店长佣金比</view>
        <view class="column-list-operation">
          <input
            class="column-list-operation-input"
            type="number"
            v-model="storeManagerCommissionRatio"
          />%
        </view>
      </view>
      <!-- end column-list -->
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-name">店员佣金比</view>
        <view class="column-list-operation">
          <input
            class="column-list-operation-input"
            type="number"
            v-model="mployeeCommissionRatio"
          />%
        </view>
      </view>
      <!-- end column-list -->
      <!-- start member-recommendation-commission-hint -->
      <view class="member-recommendation-commission-hint"
        >注：以上为自定义设置佣金比。</view
      >
      <!-- end member-recommendation-commission-hint -->
      <!-- start confirm-btn -->
      <view class="confirm-btn">确定</view>
      <!-- end confirm-btn -->
    </view>
    <!-- end commission-card -->
  </view>
  <!-- end member-recommendation-commission -->
</template>

<script>
export default {
  data() {
    return {
      // 店长佣金比
      storeManagerCommissionRatio: 70,
      // 店员佣金比
      mployeeCommissionRatio: 30,
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
};
</script>

<style lang="less" scoped>
.member-recommendation-commission {
  padding: 20rpx 30rpx 0 30rpx;
  .commission-card {
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 0 50rpx;
    padding-bottom: 40rpx;
    .column-list {
      display: flex;
      justify-content: space-between;
      box-sizing: border-box;
      padding: 36rpx 0;
      border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
      .column-list-name {
        font-size: 24rpx;
        font-weight: 400;
        color: #999999;
      }
      .column-list-operation {
        display: flex;
        align-items: center;
        font-size: 28rpx;
        font-weight: 500;
        color: #333333;
        .column-list-operation-input {
          width: 80rpx;
          text-align: right;
          align-items: center;
          font-size: 28rpx;
          font-weight: 500;
          color: #333333;
        }
      }
    }
    .member-recommendation-commission-hint {
      margin-top: 20rpx;
      font-size: 24rpx;
      font-weight: 400;
      color: #666666;
    }
    .confirm-btn {
      margin-top: 60rpx;
      width: 100%;
      height: 80rpx;
      background: #c78125;
      border-radius: 16rpx;
      font-size: 32rpx;
      font-weight: 600;
      color: #ffffff;
      text-align: center;
      line-height: 80rpx;
    }
  }
}
</style>
