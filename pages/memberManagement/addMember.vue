<template>
  <!-- start add-member -->
  <view class="add-member">
    <!-- start add-member-card -->
    <view class="add-member-card">
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-label">会员姓名</view>
        <view class="column-list-content justify-align">
          <input class="column-list-val" placeholder="请输入会员姓名" />
        </view>
      </view>
      <!-- end column-list -->
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-label">手机号</view>
        <view class="column-list-content justify-align">
          <input class="column-list-val" placeholder="请输入手机号" />
        </view>
      </view>
      <!-- end column-list -->
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-label">类型</view>
        <view class="column-list-content justify-align">
          <text class="column-list-val">会员-年卡</text>
          <img src="/static/images/right-icon.png" class="operation-icon" />
        </view>
      </view>
      <!-- end column-list -->
      <!-- start confirm-btn -->
      <view class="confirm-btn">确定</view>
      <!-- end confirm-btn -->
    </view>
    <!-- end add-member-card -->
    <!-- start hint-info -->
    <view class="hint-info">账号为手机号码，初始密码8888888。登录后请及时修改密码。</view>
    <!-- end hint-info -->
  </view>
  <!-- end add-member -->
</template>

<script>
export default {
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
};
</script>

<style lang="less" scoped>
.add-member {
  padding: 20rpx 30rpx 0 30rpx;
  .add-member-card {
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 0 50rpx;
    padding-bottom: 40rpx;
  }
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

.hint-info {
  margin-top: 20rpx;
  margin-bottom: 40rpx;
  font-size: 24rpx;
  font-weight: 400;
  color: #999999;
  text-align: center;
}

.column-list {
  display: flex;
  justify-content: space-between;
  box-sizing: border-box;
  padding: 36rpx 0;
  border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
  .column-list-label {
    width: 202rpx;
    .required {
      margin-right: 14rpx;
      font-size: 24rpx;
      font-weight: 400;
      color: #ff0000;
    }
  }
  .column-list-content {
    flex: 1;
    .column-list-val {
      font-size: 28rpx;
      font-weight: 500;
      color: #333333;
    }
    .operation-icon {
      width: 12rpx;
      height: 20rpx;
    }
  }
  .justify-align {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}
</style>
