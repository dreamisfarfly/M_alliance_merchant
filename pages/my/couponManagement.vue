<template>
  <!-- start coupon-management -->
  <view class="coupon-management">
    <!-- start 切换栏 -->
    <u-tabs-swiper
      inactive-color="#999999"
      active-color="#333333"
      :bar-style="tableBarStyle"
      ref="tabs"
      :list="tabMenu"
      :is-scroll="false"
      bar-height="6"
      bar-width="54"
      font-size="28"
      :current="swiperCurrent"
      @change="tabsChange"
    >
    </u-tabs-swiper>
    <!-- start 切换栏 -->
    <!-- start coupon-management-content -->
    <view class="coupon-management-content">
      <!-- start coupon-management-list -->
      <view class="coupon-management-list" v-for="(item, key) in couponList" :key="key">
        <!-- start coupon-management-type-card -->
        <view class="coupon-management-type-card">
          <img
            v-if="item.type == 0"
            class="coupon-management-type-icons"
            src="/static/images/discount-coupon-magcard.png"
          />
          <img
            v-if="item.type == 1"
            class="coupon-management-type-icons"
            src="/static/images/discount-coupon-consumer-voucher.png"
          />
          <img
            v-if="item.type == 2"
            class="coupon-management-type-icons"
            src="/static/images/discount-coupon-cash-coupon.png"
          />
        </view>
        <!-- end coupon-management-type-card -->
        <!-- start coupon-management-info-card -->
        <view class="coupon-management-info-card">
          <!-- start coupon-management-info-card-header -->
          <view class="coupon-management-info-card-header">
            <view class="coupon-management-info-card-header-name"
              >{{item.title}}</view
            >
            <view class="addition-btn" v-if="swiperCurrent == 0">下架</view>
            <view class="addition-btn" v-if="swiperCurrent == 1">添加</view>
          </view>
          <!-- end coupon-management-info-card-header -->
          <!-- start coupon-management-info-card-value -->
          <view class="coupon-management-info-card-value">
            <template v-if="item.type==0">价值 188元</template>
            <template v-if="item.type==1">满100减10元现金券</template>
            <template v-if="item.type==2">现金直接抵扣</template>
          </view>
          <!-- end coupon-management-info-card-value -->
          <!-- start coupon-management-info-card-separator -->
          <view class="coupon-management-info-card-separator"></view>
          <!-- end coupon-management-info-card-separator -->
          <!-- start coupon-management-info-card-expiration-time -->
          <view class="coupon-management-info-card-expiration-time">
            <text>领取后30天有效</text>
            <text v-if="swiperCurrent == 0">10家门店适用></text>
          </view>
          <!-- end coupon-management-info-card-expiration-time -->
        </view>
        <!-- end coupon-management-info-card -->
      </view>
      <!-- end coupon-management-list -->
    </view>
    <!-- end coupon-management-content -->
  </view>
  <!-- end coupon-management -->
</template>

<script>
export default {
  data() {
    return {
      //  swiper组件的current值
      swiperCurrent: 0, //0:优惠劵列表 1:添加优惠劵
      // tab栏滑块样式
      tableBarStyle: {
        background: "linear-gradient(270deg, #D99A48 0%, #F5C684 100%)",
      },
      // 选项卡标题
      tabMenu: [
        {
          name: "优惠券列表",
        },
        {
          name: "添加优惠券",
        },
      ],
      // 优惠劵列表
      couponList: [
        {
          type: 0,
          title: "洁牙卡一次",
        },
        {
          type: 1,
          title: "10元消费券",
        },
        {
          type: 2,
          title: "10元现金券",
        },
      ],
    };
  },
  methods: {
    // tabs通知swiper切换
    tabsChange(index) {
      this.swiperCurrent = index;
    },
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
};
</script>

<style lang="less" scoped>
.coupon-management-content {
  padding: 0 14rpx;
  padding-top: 12rpx;
  .coupon-management-list {
    width: 100%;
    height: 240rpx;
    background: url("/static/images/discount-coupon-bak.png");
    background-size: 100% 100%;
    display: flex;
    .coupon-management-type-card {
      width: 152rpx;
      height: 100%;
      padding-left: 30rpx;
      box-sizing: border-box;
      display: flex;
      align-items: center;
      .coupon-management-type-icons {
        width: 98rpx;
        height: 106rpx;
      }
    }
    .coupon-management-info-card {
      flex: 1;
      padding: 6rpx 46rpx 18rpx 16rpx;
      box-sizing: border-box;
      .coupon-management-info-card-header {
        padding-top: 24rpx;
        display: flex;
        align-items: center;
        justify-content: space-between;
        box-sizing: border-box;
        .coupon-management-info-card-header-name {
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
    .coupon-management-info-card-value {
      margin-top: 16rpx;
      font-size: 24rpx;
      font-weight: 400;
      color: #999999;
    }
    .coupon-management-info-card-separator {
      margin-top: 22rpx;
      width: 100%;
      height: 2rpx;
      background: #f0f0f0;
    }
    .coupon-management-info-card-expiration-time {
      margin-top: 18rpx;
      font-size: 20rpx;
      font-weight: 400;
      color: #999999;
      display: flex;
      justify-content: space-between;
    }
  }
}
</style>
