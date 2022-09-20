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
      <template v-if="swiperCurrent == 0">
        <CouponCard
          scene="listShow"
          :coupon="item"
          v-for="(item, key) in couponList"
          :key="key"
        />
      </template>
      <template v-if="swiperCurrent == 1">
        <CouponCard
          scene="listAdd"
          :coupon="item"
          v-for="(item, key) in couponList"
          :key="key"
        />
      </template>
    </view>
    <!-- end coupon-management-content -->
  </view>
  <!-- end coupon-management -->
</template>

<script>
import CouponCard from "@/components/couponCard/couponCard.vue";
export default {
  data() {
    return {
      //  swiper组件的current值
      swiperCurrent: 0,
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
  components: { CouponCard },
};
</script>

<style lang="less" scoped>
.coupon-management-content {
  padding: 0 14rpx;
  padding-top: 12rpx;
}
</style>
