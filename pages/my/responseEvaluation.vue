<template>
  <!-- start response-evaluation -->
  <view class="response-evaluation">
    <!-- start response-evaluation-card -->
    <view class="response-evaluation-card">
      <!-- start comment-list -->
      <view class="comment-list">
        <!-- start comment-list-header -->
        <view class="comment-list-header">
          <img class="user-buddha" src="" />
          <view class="comment-info">
            <view class="user-comment-info">
              <view class="user-name">王丽丽</view>
              <view class="user-time">2020-08-08</view>
            </view>
            <score style="margin-top: 6rpx;" :evaluationScore="4" />
          </view>
        </view>
        <!-- end comment-list-header -->
        <!-- start comment-list-content -->
        <view class="comment-list-content">
          <view class="comment-content"
            >不好意思评价晚了，非常好的店家，东西很喜欢！买来这个是送人的她很喜欢卖家的贴心让我感到很温暖。</view
          >
          <view class="comment-img-content">
            <img
              src=""
              class="comment-img"
              v-for="(item, key) in 3"
              :key="key"
            />
          </view>
        </view>
        <!-- end comment-list-content -->
        <!-- start comment-list-footer -->
        <view class="comment-list-footer">
          <view class="comment-data-info">
            <view class="browse">
              <img
                class="comment-data-icon"
                src="/static/images/browse-icon.png"
              />
              <text class="comment-data-count">1000</text>
            </view>
            <view class="msg">
              <img
                class="comment-data-icon"
                src="/static/images/msg-icon.png"
              />
              <text class="comment-data-count">1</text>
            </view>
          </view>
        </view>
        <!-- end comment-list-footer -->
      </view>
      <!-- end comment-list -->
      <!-- start comment-details -->
      <view class="comment-details">
        <!-- start comment-details-list -->
        <view class="comment-details-list" v-for="(item, key) in 3" :key="key">
          <img src="" class="comment-details-list-img" />
          <view class="comment-details-list-info">
            <view class="justify-align">
              <view class="user-name">王丽丽</view>
              <view class="comment-data-info">
                <view class="browse">
                  <img
                    class="comment-data-icon"
                    src="/static/images/browse-icon.png"
                  />
                  <text class="comment-data-count">1000</text>
                </view>
                <view class="msg">
                  <img
                    class="comment-data-icon"
                    src="/static/images/msg-icon.png"
                  />
                  <text class="comment-data-count">1</text>
                </view>
              </view>
            </view>
            <view class="user-time" style="margin-top: 4rpx;line-height: 14px;">2020-08-08</view>
            <view class="comment-content" style="margin-top: 14rpx">
              不好意思评价晚了，非常好的店家，东西很喜欢！
              买来这个是送人的她很喜欢卖家的贴心让我感到 很温暖。
            </view>
          </view>
        </view>
        <!-- end comment-details-list -->
      </view>
      <!-- end comment-details -->
    </view>
    <!-- end response-evaluation-card -->
  </view>
  <!-- end response-evaluation -->
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
.response-evaluation {
  padding: 20rpx 30rpx;
  .response-evaluation-card {
    background: #ffffff;
    box-shadow: 0 8rpx 16px 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 0 30rpx;
    box-sizing: border-box;
  }
}

.comment-list {
  box-sizing: border-box;
  padding-bottom: 24rpx;
  border-bottom: 2rpx solid rgba(0, 0, 0, 0.05);
  .comment-list-header {
    padding: 30rpx 0;
    display: flex;
    .user-buddha {
      width: 70rpx;
      height: 70rpx;
      border-radius: 50% 50%;
    }
    .comment-info {
      flex: 1;
      margin-left: 26rpx;
      .user-comment-info {
        display: flex;
        justify-content: space-between;
      }
    }
  }
  .comment-list-content {
    .comment-img-content {
      display: flex;
      margin-top: 24rpx;
      .comment-img {
        margin-right: 20rpx;
        width: 120rpx;
        height: 120rpx;
      }
    }
  }
  .comment-list-footer {
    display: flex;
    margin-top: 48rpx;
  }
}

.comment-content {
  font-size: 24rpx;
  font-weight: 400;
  color: #333333;
  line-height: 34rpx;
}

.user-name {
  font-size: 28rpx;
  font-weight: 500;
  color: #333333;
  line-height: 40rpx;
}
.user-time {
  font-size: 20rpx;
  font-weight: 400;
  color: #999999;
}

.comment-data-info {
  margin-left: auto;
  display: flex;
  .comment-data-icon {
    width: 28rpx;
    height: 28rpx;
  }
  .browse {
    display: flex;
    align-items: center;
  }
  .msg {
    margin-left: 44rpx;
    display: flex;
    align-items: center;
  }
  .comment-data-count {
    margin-left: 10rpx;
    font-size: 20rpx;
    font-weight: 400;
    color: #333333;
  }
}

.comment-details {
  .comment-details-list {
    padding-top: 30rpx;
    padding-bottom: 60rpx;
    display: flex;
    .comment-details-list-img {
      width: 40rpx;
      height: 40rpx;
      border-radius: 50% 50%;
    }
    .comment-details-list-info {
      margin-left: 20rpx;
    }
  }
}

.justify-align {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
