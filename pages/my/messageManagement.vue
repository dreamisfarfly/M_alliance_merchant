<template>
  <!-- start 消息管理 -->
  <view>
    <!-- start 导航栏 -->
    <u-navbar
      :is-back="false"
      title="消息管理"
      :background="background"
      title-color="#333333"
      title-size="32"
      :title-bold="true"
    >
      <template slot="right">
        <text class="add-message" @click="jump('/pages/my/addMessage')"
          >添加</text
        >
      </template>
    </u-navbar>
    <!-- end 导航栏 -->
    <!-- start message-management-content -->
    <view class="message-management-content">
      <!-- start message-management-list -->
      <view class="message-management-list" v-for="(item, key) in 6" :key="key">
        <view class="message-management-info">
          <img src="" class="message-icon" />
          <view class="message-info">
            <view class="message-info-name">浓情端午节</view>
            <view class="message-info-time">2022年6月18日 12：30</view>
          </view>
        </view>
        <view class="message-management-del">删除</view>
      </view>
      <!-- end message-management-list -->
    </view>
    <!-- end message-management-content -->
  </view>
  <!-- end 消息管理 -->
</template>

<script>
export default {
  data() {
    return {
      // 导航栏背景
      background: {
        backgroundColor: "#FFFFFF",
      },
    };
  },
  methods: {
    // 跳转
    jump(path) {
      uni.navigateTo({
        url: path,
      });
    },
  },
};
</script>

<style lang="less" scoped>
.add-message {
  margin-right: 50rpx;
  font-size: 32rpx;
  font-weight: 500;
  color: #333333;
}
.message-management-content {
  padding: 0 30rpx;
  .message-management-list {
    margin-top: 20rpx;
    padding: 28rpx 30rpx 30rpx 30rpx;
    box-sizing: border-box;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .message-management-info {
      display: flex;
      .message-icon {
        width: 106rpx;
        height: 80rpx;
      }
      .message-info {
        margin-left: 20rpx;
        .message-info-name {
          font-size: 28rpx;
          font-weight: 500;
          color: #333333;
        }
        .message-info-time {
          margin-top: 12rpx;
          font-size: 24rpx;
          font-weight: 400;
          color: #999999;
        }
      }
    }
    .message-management-del {
      width: 92rpx;
      height: 42rpx;
      border-radius: 8rpx;
      border: 2rpx solid #ff7265;
      font-size: 20rpx;
      font-weight: 500;
      color: #ff7265;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
}
</style>
