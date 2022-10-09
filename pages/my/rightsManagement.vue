<template>
  <!-- start rights-management -->
  <view class="rights-management">
    <!-- start rights-management-card -->
    <view class="rights-management-card">
      <!-- start rights-management-card-grouping -->
      <view class="rights-management-card-grouping">
        <view class="grouping-name">会员折扣</view>
        <view class="grouping-content">
          <view class="grouping-list grouping-list-halving-line">
            <input
              class="grouping-list-hint"
              placeholder="折扣 （仅支持一位小数）"
            />
            <text class="grouping-list-val">9折</text>
          </view>
          <view class="discount-contet">
            <view class="discount-contet-title">折扣说明</view>
            <view class="textarea-vessel">
              <textarea
                style="height: 126rpx"
                class="general-textarea"
                placeholder="请输入折扣说明"
              ></textarea>
            </view>
          </view>
        </view>
      </view>
      <!-- end rights-management-card-grouping -->
      <!-- start rights-management-card-grouping -->
      <view class="rights-management-card-grouping" style="margin-top: 28rpx">
        <view class="grouping-name">其他特权</view>
        <view class="grouping-content">
          <view class="textarea-vessel">
            <textarea
              style="height: 172rpx"
              class="general-textarea"
              placeholder="请输入其他特权"
            ></textarea>
          </view>
        </view>
      </view>
      <!-- end rights-management-card-grouping -->
      <!-- start rights-management-card-grouping -->
      <view class="rights-management-card-grouping" style="margin-top: 28rpx">
        <view class="grouping-name">预约规则</view>
        <view class="grouping-content">
          <view class="grouping-list">
            <view class="grouping-list-hint">是否需要预约</view>
            <view class="grouping-list-val">
              <text>是</text>
              <img
                class="grouping-list-operate-icon"
                src="/static/images/right-icon.png"
              />
            </view>
          </view>
          <view class="grouping-list">
            <view class="grouping-list-hint">提前预约时间</view>
            <view class="grouping-list-val">
              <text>6小时</text>
              <img
                class="grouping-list-operate-icon"
                src="/static/images/right-icon.png"
              />
            </view>
          </view>
        </view>
      </view>
      <!-- end rights-management-card-grouping -->
      <!-- start confirm-btn -->
      <view class="confirm-btn">确定</view>
      <!-- end confirm-btn -->
    </view>
    <!-- end rights-management-card -->
  </view>
  <!-- end rights-management -->
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
.rights-management {
  padding: 0 30rpx;
  .rights-management-card {
    margin-top: 20rpx;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 30rpx 50rpx 38rpx 50rpx;
    box-sizing: border-box;
    .rights-management-card-grouping {
      padding-bottom: 30rpx;
      border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
      .grouping-name {
        font-size: 24rpx;
        font-weight: 500;
        color: #333333;
      }
      .grouping-content {
        margin-top: 32rpx;
        .grouping-list {
          display: flex;
          align-items: center;
          justify-content: space-between;
          padding: 14rpx 0;
          .grouping-list-operate-icon {
            margin-left: 12rpx;
            width: 12rpx;
            height: 20rpx;
          }
          .grouping-list-hint {
            font-size: 24rpx;
            font-weight: 400;
            color: #999999;
          }
          .grouping-list-val {
            font-size: 28rpx;
            font-weight: 500;
            color: #333333;
          }
          .grouping-list-title {
            font-size: 24rpx;
            font-weight: 400;
            color: #999999;
          }
        }
        .discount-contet {
          .discount-contet-title {
            margin-top: 14rpx;
            margin-bottom: 38rpx;
            font-size: 24rpx;
            font-weight: 400;
            color: #999999;
          }
        }
        .grouping-list-halving-line {
          border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
        }
      }
    }
  }
}

.textarea-vessel {
  width: 100%;
  background: #f5f5f5;
  border-radius: 16rpx;
  padding: 8rpx 12rpx;
  box-sizing: border-box;
}

.general-textarea {
  width: 100%;
  font-size: 24rpx;
  font-weight: 400;
  color: #333333;
  line-height: 44rpx;
}

.confirm-btn {
  margin-top: 58rpx;
  width: 100%;
  height: 80rpx;
  background: #c78125;
  border-radius: 16rpx;
  font-size: 32rpx;
  font-weight: 600;
  color: #ffffff;
  line-height: 80rpx;
  text-align: center;
}
</style>
