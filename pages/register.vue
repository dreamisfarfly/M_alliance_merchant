<template>
  <!-- start purchase-upgrade -->
  <view class="purchase-upgrade">
    <!-- start member-name -->
    <view class="member-name">店铺注册</view>
    <!-- end member-name -->
    <!-- start equity -->
    <view class="equity">
      <!-- start m-alliance-icon -->
      <img class="m-alliance-icon" src="/static/images/m-alliance-icon.png" />
      <!-- end m-alliance-icon -->
      <!-- start equity-name -->
      <view class="equity-name">注册服务商尊享两大权益</view>
      <!-- end equity-name -->
      <!-- start separator -->
      <view class="separator"></view>
      <!-- end separator -->
      <!-- start equity-subheading -->
      <view class="equity-subheading"
        >Registered service providers enjoy two benefits</view
      >
      <!-- end equity-subheading -->
      <view class="equity-content">
        <view class="equity-list">1、签约门店获收益</view>
        <view class="equity-list">2、会员注册获收益</view>
      </view>
    </view>
    <!-- end equity -->
    <!-- start member-vessel -->
    <view class="member-vessel">
      <!-- start 必填信息 -->
      <view class="member-vessel-column">
        <view class="member-vessel-title">必填信息</view>
        <view class="required-info-conent">
          <view class="required-info-list">
            <label class="required-info-list-name">姓名</label>
            <input
              class="required-info-list-input"
              type="text"
              placeholder="请输入姓名"
            />
          </view>
          <view class="required-info-list">
            <label class="required-info-list-name">手机</label>
            <input
              class="required-info-list-input"
              type="text"
              placeholder="请输入手机"
              maxlength="11"
            />
          </view>
          <view class="required-info-list">
            <label class="required-info-list-name">密码</label>
            <input
              class="required-info-list-input"
              type="text"
              placeholder="请输入密码"
            />
          </view>
          <view class="required-info-list">
            <label class="required-info-list-name">确认密码</label>
            <input
              class="required-info-list-input"
              type="text"
              placeholder="请输入确认密码"
            />
          </view>
        </view>
      </view>
      <!-- end 必填信息 -->
      <!-- start 付费信息 -->
      <view class="member-vessel-column">
        <view class="member-vessel-title">付费信息</view>
        <view class="combo-content">
          <view
            class="combo-list"
            v-for="(item, key) in comboList"
            :key="key"
            :style="{ 'margin-left': key > 0 ? '56rpx' : '' }"
            @click="defaultOption = key"
          >
            <view v-if="defaultOption == key" class="select-combo"></view>
            <view class="combo-list-title">{{ item.name }}</view>
            <view class="combo-list-price">
              <text style="font-size: 20rpx">￥</text>{{ item.price }}
            </view>
            <view class="combo-list-time">{{ item.duration }}天</view>
          </view>
        </view>
      </view>
      <!-- end 付费信息 -->
      <view class="payment-btn">
        <text class="payment-btn-font">立即支付</text>
      </view>
      <view class="activation-code">输入激活码></view>
    </view>
    <!-- end member-vessel -->
  </view>
  <!-- end purchase-upgrade -->
</template>

<script>
export default {
  data() {
    return {
      // 套餐列表
      comboList: [
        {
          name: "月卡会员",
          price: 100.0,
          duration: 30,
        },
        {
          name: "年卡会员",
          price: 100.0,
          duration: 30,
        },
        {
          name: "年卡会员",
          price: 100.0,
          duration: 365,
        },
      ],
      // 默认选择套餐
      defaultOption: 0,
    };
  },
};
</script>

<style scoped lang="scss">
.purchase-upgrade {
  width: 100%;
  background: url("/static/images/purchase-upgrade-bak.png");
  background-size: 100% 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0 30rpx;
  padding-bottom: 18rpx;
  box-sizing: border-box;
  .member-name {
    padding-top: 106rpx;
    font-size: 32rpx;
    font-family: PingFangSC-Medium, PingFang SC;
    font-weight: 500;
    color: #ffffff;
  }
  .equity {
    width: 100%;
    //height: 476rpx;
    background: url("/static/images/equity-bak.png");
    background-size: 100% 100%;
    border-radius: 16rpx;
    display: flex;
    align-items: center;
    flex-direction: column;
    padding-bottom: 38rpx;
    margin-top: 88rpx;
    box-sizing: border-box;
    .m-alliance-icon {
      margin-top: 54rpx;
      width: 134rpx;
      height: 150rpx;
      flex-shrink: 0;
    }
    .equity-name {
      margin-top: 50rpx;
      font-family: AlimamaShuHeiTi;
      font-size: 36rpx;
      color: #ffc98e;
      text-shadow: 0 2rpx 2rpx rgba(0, 0, 0, 0.5);
      background: linear-gradient(270deg, #ffefd6 0%, #f1c18c 100%);
      -webkit-text-fill-color: transparent;
      -webkit-background-clip: text;
      letter-spacing: 4rpx;
    }
    .separator {
      margin-top: 14rpx;
      width: 396rpx;
      height: 2rpx;
      background: rgba(253, 233, 205, 0.3);
    }
    .equity-subheading {
      margin-top: 10rpx;
      font-size: 8rpx;
      color: #ffc98e;
      letter-spacing: 2px;
    }
    .equity-content {
      margin-top: 44rpx;
      width: 100%;
      display: flex;
      align-items: center;
      padding: 0 48rpx;
      box-sizing: border-box;
      justify-content: space-between;
      .equity-list {
        width: 286rpx;
        height: 54rpx;
        border: 2rpx solid #ffdaad;
        border-radius: 28rpx;
        font-size: 24rpx;
        font-weight: 500;
        color: #ffdaad;
        letter-spacing: 2rpx;
        display: flex;
        align-items: center;
        justify-content: center;
      }
    }
  }
  .member-vessel {
    margin-top: 30rpx;
    width: 100%;
    background: linear-gradient(180deg, #2a2827 0%, #100e0d 100%);
    border-radius: 16rpx;
    border: 2rpx solid rgba(246, 225, 187, 1);
    padding: 0 50rpx;
    display: flex;
    align-items: center;
    flex-direction: column;
    padding-bottom: 100rpx;
    box-sizing: border-box;
    .member-vessel-column {
      padding-top: 30rpx;
      width: 100%;
      .member-vessel-title {
        font-size: 28rpx;
        color: #ffc98e;
        text-shadow: 0 2rpx 2rpx rgba(0, 0, 0, 0.5);
        background: linear-gradient(270deg, #ffefd6 0%, #f1c18c 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        text-align: left;
      }
    }
    .required-info-conent {
      margin-top: 20rpx;
      .required-info-list {
        display: flex;
        padding: 28rpx 0;
        box-sizing: border-box;
        border-bottom: 2rpx solid rgba(255, 255, 255, 0.1);
        .required-info-list-name {
          font-size: 24rpx;
          font-weight: 400;
          color: #999999;
          width: 154rpx;
          display: flex;
          align-items: center;
        }
        .required-info-list-input {
          font-size: 28rpx;
          font-weight: 500;
          color: #ffffff;
        }
      }
    }
    .combo-content {
      margin-top: 40rpx;
      display: flex;
      .combo-list {
        width: 160rpx;
        height: 160rpx;
        background: #26282a;
        border-radius: 18rpx;
        border: 2rpx solid #fff4e7;
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;
        box-sizing: content-box;
        .select-combo {
          position: absolute;
          width: 50rpx;
          height: 48rpx;
          top: 0;
          right: 0;
          background: url("/static/images/select-combo-icon.png");
          background-size: 100% 100%;
        }
        .combo-list-title {
          margin-top: 20rpx;
          font-size: 22rpx;
          font-weight: 400;
          color: #ffffff;
          text-align: center;
        }
        .combo-list-price {
          margin-top: 12rpx;
          font-size: 38rpx;
          font-weight: 400;
          color: #ebc398;
          text-align: center;
        }
        .combo-list-time {
          position: absolute;
          bottom: 0;
          left: 0;
          right: 0;
          width: 100%;
          height: 42rpx;
          background: #ffdaad;
          border-radius: 0 0 18rpx 18rpx;
          font-size: 22rpx;
          font-weight: 600;
          color: #333333;
          display: flex;
          align-items: center;
          justify-content: center;
        }
      }
    }
    .payment-btn {
      margin-top: 68rpx;
      width: 100%;
      height: 80rpx;
      background: #494745;
      box-shadow: 0 6rpx 16rpx 0 rgba(17, 15, 13, 0.39);
      border-radius: 16rpx;
      border: 2rpx solid rgba(255, 218, 173, 1);
      text-align: center;
      line-height: 80rpx;

      .payment-btn-font {
        font-size: 32rpx;
        font-weight: 600;
        color: #ffc98e;
        text-shadow: 0px 1px 1px rgba(0, 0, 0, 0.5);
        background: linear-gradient(270deg, #ffefd6 0%, #f1c18c 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
      }
    }
    .activation-code {
      margin-top: 36rpx;
      font-weight: 600;
      text-shadow: 0 2rpx 2rpx rgba(0, 0, 0, 0.5);
      background: linear-gradient(270deg, #ffefd6 0%, #f1c18c 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-size: 24rpx;
      color: #ffc98e;
    }
  }
}
</style>
