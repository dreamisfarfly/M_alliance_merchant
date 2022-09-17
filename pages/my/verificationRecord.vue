<template>
  <!-- start 核销记录 -->
  <view>
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
    <!-- start verification-record -->
    <view class="verification-record">
        <!-- start 用券记录 -->
        <template v-if="swiperCurrent==0">
          <UseCouponsRecordCard :coupons="{type:0}"></UseCouponsRecordCard>
        </template>
        <!-- end 用券记录 -->
        <!-- start 消费记录 -->
        <template v-if="swiperCurrent==1"></template>
        <!-- end 消费记录 -->
    </view>
    <!-- end verification-record -->
  </view>
  <!-- end 核销记录 -->
</template>

<script>
import UseCouponsRecordCard from '@/components/useCouponsRecordCard/useCouponsRecordCard.vue';
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
                    name: "用券记录",
                },
                {
                    name: "消费记录",
                },
            ],
        };
    },
    mounted() {
        var a = document.getElementsByClassName("uni-page-head-hd")[0];
        a.style.opacity = 0;
    },
    methods: {
        // tabs通知swiper切换
        tabsChange(index) {
            this.swiperCurrent = index;
        },
    },
    components: { UseCouponsRecordCard }
};
</script>

<style lang="less" scoped>
.verification-record {
  padding: 0 14rpx;
  padding-top: 12rpx;
}
</style>
