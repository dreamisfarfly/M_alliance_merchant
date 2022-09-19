<template>
  <!-- start 会员管理 -->
  <view>
    <!-- start 导航栏 -->
    <u-navbar
      :is-back="false"
      title="会员管理"
      :background="background"
      title-color="#333333"
      title-size="32"
      :title-bold="true"
    >
      <template slot="right">
        <text class="release-message">发布消息</text>
      </template>
    </u-navbar>
    <!-- end 导航栏 -->
    <!-- start member-management -->
    <view class="member-management">
      <!-- start 搜索 -->
      <search v-model="searchValue" @searchFun="searchFun"></search>
      <!-- end 搜索 -->
      <!-- start member-coun-info -->
      <view class="member-coun-info">
        已添加会员：<text style="color: #c78125">55</text>/1000
        {{ searchValue }}</view
      >
      <!-- end member-coun-info -->
      <!-- start member-content -->
      <view class="member-content">
        <!-- start member-list -->
        <view class="member-list" v-for="(item, key) in 6" :key="key">
          <img class="member-list-buddha" src="" />
          <view class="member-list-info">
            <view class="member-user-info">
              <view class="user-info">
                <text class="user-info-name">李丽丽</text>
                <view class="member-status">正常</view>
              </view>
              <view class="member-info">
                <img class="vip-icon" src="/static/images/vip-icon.png" />
                <text class="vip-name">门店会员</text>
              </view>
            </view>
            <view class="member-list-info-phone">156****9999</view>
            <view
              class="member-list-info-limited"
              :style="{ color: 1 == 1 ? 'red' : '' }"
              >有效期至2022年10月9日</view
            >
          </view>
        </view>
        <!-- end member-list -->
      </view>
      <!-- end member-content -->
    </view>
    <!-- end member-management -->
    <!-- start add-vip -->
    <img
      class="add-vip"
      src="/static/images/add-vip.png"
      @click="jump('/pages/memberManagement/addMember')"
    />
    <!-- end add-vip -->
  </view>
  <!-- end 会员管理 -->
</template>

<script>
import search from "@/components/search/search.vue";
export default {
  components: { search },
  data() {
    return {
      // 导航栏背景
      background: {
        backgroundColor: "#FFFFFF",
      },
      // 搜索值
      searchValue: null,
    };
  },
  methods: {
    // 搜索
    searchFun() {
      console.log(this.searchValue);
    },
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
.release-message {
  margin-right: 18rpx;
  font-size: 32rpx;
  font-weight: 500;
  color: #c78125;
}
.member-management {
  padding: 0 30rpx;
  padding-top: 16rpx;
  box-sizing: border-box;
}
.member-coun-info {
  margin-top: 40rpx;
  font-size: 28rpx;
  font-weight: 500;
  color: #333333;
}
.member-content {
  padding-bottom: 30rpx;
  .member-list {
    margin-top: 20rpx;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 30rpx;
    box-sizing: border-box;
    display: flex;
    .member-list-buddha {
      width: 100rpx;
      height: 100rpx;
      border-radius: 50%;
    }
    .member-list-info {
      flex: 1;
      margin-left: 20rpx;
      .member-user-info {
        display: flex;
        align-items: center;
        justify-content: space-between;
        box-sizing: border-box;
        .user-info {
          display: flex;
          align-items: center;
          .user-info-name {
            font-size: 28rpx;
            font-weight: 500;
            color: #333333;
          }
          .member-status {
            margin-left: 16rpx;
            width: 64rpx;
            height: 30rpx;
            border-radius: 8rpx;
            border: 2rpx solid #60b251;
            font-size: 16rpx;
            font-weight: 500;
            color: #60b251;
            text-align: center;
            line-height: 30rpx;
          }
        }
        .member-info {
          display: flex;
          align-items: center;
          .vip-icon {
            width: 24rpx;
            height: 24rpx;
          }
          .vip-name {
            margin-left: 8rpx;
            font-size: 22rpx;
            font-weight: 400;
            color: #333333;
          }
        }
      }
      .member-list-info-phone {
        font-size: 24rpx;
        font-weight: 400;
        color: #999999;
      }
      .member-list-info-limited {
        margin-top: 8rpx;
        font-size: 20rpx;
        font-weight: 400;
        color: #999999;
      }
    }
  }
}

.add-vip {
  position: fixed;
  bottom: 188rpx;
  right: 40rpx;
  width: 100rpx;
  height: 100rpx;
}
</style>
