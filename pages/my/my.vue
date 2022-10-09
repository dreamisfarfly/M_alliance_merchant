<template>
  <!-- start 我的 -->
  <view>
    <!-- start my-header -->
    <view class="my-header">
      <!-- start my-header-user-info -->
      <view class="my-header-user-info">
        <!-- start user-info -->
        <view class="user-info">
          <img class="user-buddha" src="" />
          <view class="info">
            <view class="user-name-vessel">
              <text class="user-name">商户名丽丽</text>
              <img
                class="shopkeeper-icon"
                src="/static/images/shopkeeper-icon.png"
              />
            </view>
            <view class="user-account">账号：534536</view>
          </view>
        </view>
        <!-- end user-info -->
        <!-- start ewm-icon -->
        <img class="ewm-icon" src="/static/images/ewm-icon.png" />
        <!-- end ewm-icon -->
      </view>
      <!-- end my-header-user-info -->
      <!-- start data-info -->
      <view class="data-info">
        <view class="data-info-operation">
          <text class="complete-information">资料完善度 50%</text>
          <text class="to-perfect" @click="jump('/pages/my/perfectInformation')"
            >去完善>></text
          >
        </view>
        <view class="progress-bar-vessel">
          <view class="progress-bar">
            <view
              class="schedule"
              :style="{ width: scheduleCount + '%' }"
            ></view>
          </view>
        </view>
      </view>
      <!-- end data-info -->
    </view>
    <!-- end my-header -->
    <view class="my-content">
      <!-- start user-detailed -->
      <view class="user-detailed">
        <!-- start member-info -->
        <view class="member-info">
          <view class="member-info-list">
            <view class="member-info-list-count"
              >12<text class="unit">个</text></view
            >
            <view class="member-info-list-vip-name">门店会员</view>
          </view>
          <view class="member-info-list">
            <view class="member-info-list-count"
              >130<text class="unit">个</text></view
            >
            <view class="member-info-list-vip-name">直属会员</view>
          </view>
        </view>
        <!-- end member-info -->
        <!-- start commission -->
        <view class="commission">
          <view class="commission-info">
            <view class="commission-info-count">2000.00</view>
            <view class="commission-info-name">我的佣金</view>
          </view>
          <view class="commission-operation">
            <view
              class="withdrawal-record"
              @click="jump('/pages/my/withdrawalRecord')"
              >提现记录</view
            >
            <view class="to-withdrawal" @click="jump('/pages/my/withdraw')"
              >去提现</view
            >
          </view>
        </view>
        <!-- start commission -->
      </view>
      <!-- end user-detailed -->
      <Menu v-for="(item, key) in menuList" :key="key" :menu="item"></Menu>
    </view>
  </view>
  <!-- end 我的 -->
</template>

<script>
import Menu from "@/components/menu/menu.vue";
export default {
  data() {
    return {
      //进度 %
      scheduleCount: 20,
      // 菜单列表
      menuList: [
        {
          icon: "/static/images/commission-subsidiary-icon.png",
          name: "佣金明细",
          path: "/pages/my/commissionSubsidiary",
        },
        {
          icon: "/static/images/coupon-management-icon.png",
          name: "优惠券管理",
          path: "/pages/my/couponManagement",
        },
        {
          icon: "/static/images/rights-management-icon.png",
          name: "权益管理",
          path: "/pages/my/rightsManagement",
        },
        {
          icon: "/static/images/clerk-management-icon.png",
          name: "店员管理",
          path: "/pages/my/clerkManagement",
        },
        {
          icon: "/static/images/message-management-icon.png",
          name: "消息管理",
          path: "/pages/my/messageManagement",
        },
        {
          icon: "/static/images/see-evaluation-icon.png",
          name: "查看评价",
          path: "/pages/my/seeEvaluation",
        },
        {
          icon: "/static/images/referral-code-icon.png",
          name: "推荐码",
          path: "/pages/my/referralCode",
        },
        {
          icon: "/static/images/cancel-verification-records-icon.png",
          name: "核销记录",
          path: "/pages/my/verificationRecord",
        },
      ],
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
  methods: {
    // 跳转
    jump(path) {
      uni.navigateTo({
        url: path,
      });
    },
  },
  components: { Menu },
};
</script>

<style scoped lang="scss">
.my-header {
  width: 100%;
  height: 454rpx;
  background: url("/static/images/my-header-bak.png");
  background-size: 100% 100%;
  padding: 0 32rpx;
  padding-top: 86rpx;
  box-sizing: border-box;
  .my-header-user-info {
    display: flex;
    align-items: center;
    justify-content: space-between;
    .user-info {
      display: flex;
      .user-buddha {
        width: 136rpx;
        height: 136rpx;
        border-radius: 50% 50%;
      }
      .info {
        margin-left: 22rpx;
        .user-name-vessel {
          margin-top: 12rpx;
          display: flex;
          align-items: center;
          .user-name {
            font-size: 32rpx;
            font-weight: 500;
            color: #ffffff;
            line-height: 44rpx;
          }
          .shopkeeper-icon {
            margin-left: 20rpx;
            width: 60rpx;
            height: 30rpx;
          }
        }
        .user-account {
          margin-top: 12rpx;
          font-size: 24rpx;
          font-weight: 400;
          color: #ffffff;
          line-height: 34rpx;
        }
      }
    }
    .ewm-icon {
      width: 50rpx;
      height: 50rpx;
      margin-right: 16rpx;
    }
  }
  .data-info {
    margin-top: 22rpx;
    width: 100%;
    background: rgba(#ffffff, 0.2);
    border-radius: 16rpx;
    .data-info-operation {
      padding: 16rpx 30rpx 0rpx 30rpx;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      color: #ffffff;
      font-size: 24rpx;
      .complete-information {
        font-weight: 400;
      }
      .to-perfect {
        font-weight: 500;
        display: flex;
        align-items: center;
      }
    }
  }
  .progress-bar-vessel {
    padding: 12rpx 28rpx 18rpx 24rpx;
    box-sizing: border-box;
    .progress-bar {
      background: #a37a5e;
      border-radius: 10rpx;
      width: 100%;
      height: 20rpx;
      display: flex;
      align-items: center;
      padding: 0 4rpx;
      box-sizing: border-box;
      .schedule {
        height: 12rpx;
        background: linear-gradient(270deg, #ffffff 0%, #fffcf8 100%);
        box-shadow: 0 2rpx 2rpx 0 rgba(245, 198, 132, 0.58);
        border-radius: 12rpx;
      }
    }
  }
}

.my-content {
  position: relative;
  top: -100rpx;
  width: 100%;
  padding: 0 30rpx;
  box-sizing: border-box;
  .user-detailed {
    width: 100%;
    background: #ffffff;
    box-shadow: 0 -10rpx 12rpx 0 rgba(0, 0, 0, 0.05);
    border-radius: 16rpx;
    padding: 20rpx;
    padding-top: 0rpx;
    box-sizing: border-box;
    .member-info {
      display: flex;
      .member-info-list {
        flex: 1;
        display: flex;
        align-items: center;
        flex-direction: column;
        padding: 40rpx 0;
        .member-info-list-count {
          font-size: 40rpx;
          font-weight: 600;
          color: #333333;
          .unit {
            font-size: 24rpx;
          }
        }
        .member-info-list-vip-name {
          margin-top: 10rpx;
          font-size: 24rpx;
          font-weight: 400;
          color: #999999;
        }
      }
    }
    .commission {
      width: 100%;
      background: rgba(220, 174, 98, 0.11);
      border-radius: 16rpx;
      border: 2rpx solid #ded0bb;
      padding: 14rpx 24rpx 18rpx 26rpx;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      .commission-info {
        .commission-info-count {
          font-size: 48rpx;
          font-weight: 600;
          color: #333333;
        }
        .commission-info-name {
          font-size: 20rpx;
          font-weight: 500;
          color: #999999;
          line-height: 34rpx;
        }
      }
      .commission-operation {
        display: flex;
        padding-top: 24rpx;
        .withdrawal-record {
          width: 128rpx;
          height: 50rpx;
          border-radius: 8rpx;
          border: 2rpx solid #c78125;
          font-size: 24rpx;
          font-weight: 500;
          color: #c78125;
          display: flex;
          align-items: center;
          justify-content: center;
		      box-sizing: border-box;
        }
        .to-withdrawal {
          margin-left: 20rpx;
          width: 120rpx;
          height: 50rpx;
          background: #c78125;
          border-radius: 8rpx;
          border: 2rpx solid #c78125;
          font-size: 24rpx;
          font-weight: 500;
          color: #ffffff;
          display: flex;
          align-items: center;
          justify-content: center;
		  box-sizing: border-box;
        }
      }
    }
  }
}
</style>
