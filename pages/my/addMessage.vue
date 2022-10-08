<template>
  <!-- start add-message -->
  <view class="add-message">
    <!-- start add-message-card -->
    <view class="add-message-card">
      <!-- start column-list -->
      <view class="column-list justify-align">
        <view class="column-list-label">标题</view>
        <input class="column-list-input" type="text" placeholder="请输入标题" />
      </view>
      <!-- end column-list -->
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-label">内容</view>
        <view class="textarea-vessel" style="margin-top: 30rpx">
          <textarea
            style="height: 126rpx"
            class="general-textarea"
            placeholder="请输入内容"
          ></textarea>
        </view>
      </view>
      <!-- end column-list -->
      <!-- start img-group -->
      <view class="img-group">
        <view class="img-group-name">图片</view>
        <view class="img-group-content">
          <UploadImgGroup />
        </view>
      </view>
      <!-- end img-group -->
      <!-- start confirm-btn -->
      <view class="confirm-btn">确定</view>
      <!-- end confirm-btn -->
    </view>
    <!-- end add-message-card -->
    <!-- start add-message-hint -->
    <view class="add-message-hint" style="margin-top: 20rpx"
      >温馨提示：请不要发布扰乱市场秩序的言论，否则平台会</view
    >
    <view class="add-message-hint" style="margin-bottom: 40rpx"
      >予以追究！</view
    >
    <!-- end add-message-hint -->
  </view>
  <!-- end add-message -->
</template>

<script>
import UploadImgGroup from "@/components/uploadImgGroup/uploadImgGroup.vue";
export default {
  components: { UploadImgGroup },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
};
</script>

<style lang="less" scoped>
.add-message {
  padding: 20rpx 30rpx 0 30rpx;
  .add-message-card {
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 0 50rpx;
    padding-bottom: 40rpx;
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

.img-group {
  margin-top: 38rpx;
  .img-group-name {
    font-weight: 400;
    color: #999999;
    font-size: 24rpx;
  }
  .img-group-content {
    margin-top: 36rpx;
  }
}

.column-list {
  box-sizing: border-box;
  padding: 36rpx 0;
  border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
  .column-list-label {
    width: 60rpx;
    font-size: 24rpx;
    font-weight: 400;
    color: #999999;
  }
  .column-list-input {
    font-size: 28rpx;
    font-weight: 500;
    color: #999999;
    text-align: right;
  }
  .textarea-vessel {
    width: 100%;
    background: #f5f5f5;
    border-radius: 16rpx;
    padding: 8rpx 10rpx;
    box-sizing: border-box;
    .general-textarea {
      font-size: 24rpx;
      font-weight: 400;
      color: #333333;
    }
  }
}

.justify-align {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.add-message-hint {
  font-size: 24rpx;
  font-weight: 400;
  color: #999999;
  text-align: center;
}
</style>
