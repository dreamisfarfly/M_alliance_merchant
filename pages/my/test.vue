<template>
  <!-- start 我的 -->
  <view class="my-vessel">
    <!-- start my-vessel-header -->
    <view class="my-vessel-header">
      <view class="my-vessel-header-info">
        <view>
          <view>
            <img src="" class="" />
            <view>
              <view>
                <text>商户名丽丽</text>
                <img src="" class="" />
              </view>
              <view>账号：534536</view>
            </view>
          </view>
          <img src="" class="" />
        </view>
      </view>
      <view class="my-vessel-header-perfect">
        <view>
          <text>资料完善度 50%</text>
          <text>去完善>></text>
        </view>
        <view></view>
      </view>
    </view>
    <!-- end my-vessel-header -->
    <!-- start my-vessel-content -->
    <view class="my-vessel-content">
      <!-- start store-data-vessel -->
      <view class="store-data-vessel">
        <!-- start store-data -->
        <view class="store-data">
          <!-- start store-data-list -->
          <view class="store-data-list">
            <view class="store-data-list-count"
              >12<text class="store-data-list-count-unit">个</text></view
            >
            <view class="store-data-list-label">门店会员</view>
          </view>
          <!-- end store-data-list -->
          <!-- start store-data-list -->
          <view class="store-data-list">
            <view class="store-data-list-count"
              >130<text class="store-data-list-count-unit">个</text></view
            >
            <view class="store-data-list-label">直属会员</view>
          </view>
          <!-- end store-data-list -->
        </view>
        <!-- end store-data -->
        <!-- start commission-vessel -->
        <view class="commission-vessel">
          <view class="commission-info">
            <view>2000.00</view>
            <view>我的佣金</view>
          </view>
          <view>
            <view>提现记录</view>
            <view>去提现</view>
          </view>
        </view>
        <!-- end commission-vessel -->
      </view>
      <!-- end store-data-vessel -->
    </view>
    <!-- end my-vessel-content -->
  </view>
  <!-- end 我的 -->
</template>

<script>
export default {};
</script>

<style lang="less" scoped>
.my-vessel {
  .my-vessel-header {
    width: 100%;
    height: 454rpx;
  }
  .my-vessel-content {
    position: relative;
    margin-top: -40rpx;
    padding: 0 30rpx;
    box-sizing: border-box;
    .store-data-vessel {
      padding: 0 20rpx;
      box-sizing: border-box;
      .store-data {
        display: flex;
        .store-data-list {
          flex: 1;
          display: flex;
          //align-items: center;
          padding: 0 40rpx;
          box-sizing: border-box;
          justify-content: center;
          .store-data-list-count {
            font-size: 40rpx;
            font-weight: 600;
            color: #333333;
            .store-data-list-count-unit {
              font-size: 24rpx;
            }
          }
          .store-data-list-label {
            margin-top: 10rpx;
            font-size: 24rpx;
            font-weight: 400;
            color: #999999;
          }
        }
      }
      .commission-vessel {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 14rpx 24rpx 18rpx 26rpx;
        box-sizing: border-box;
        background: rgba(220, 174, 98, 0.11);
        border-radius: 16rpx;
        border: 2rpx solid #ded0bb;
        .commission-info{
          
        }
      }
    }
  }
}
</style>
