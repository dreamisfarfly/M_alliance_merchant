<template>
  <!-- start clerk-management -->
  <view class="clerk-management">
    <!-- start clerk-management-column -->
    <view class="clerk-management-column" style="margin-top: 28rpx">
      <view class="clerk-management-column-header">
        <view class="clerk-management-column-title">会员推荐佣金</view>
      </view>
      <view class="clerk-management-column-content">
        <view class="commission-card">
          <view class="commission-info">
            <view class="commission-info-title"
              >店长佣金比：<text class="commission-data">70%</text></view
            >
            <view class="commission-info-title"
              >店员佣金比：<text class="commission-data">30%</text></view
            >
          </view>
          <view class="commission-amend">修改 ></view>
        </view>
      </view>
    </view>
    <!-- end clerk-management-column -->
    <!-- start clerk-management-column -->
    <view class="clerk-management-column" style="margin-top: 52rpx">
      <view class="clerk-management-column-header">
        <view class="clerk-management-column-title"
          >会员推荐佣金<text class="clerk-management-column-subhead"
            >（员工主要用于优惠券的核销）</text
          ></view
        >
        <view class="employee-data"
          ><text style="color: #c78125">2</text>/100</view
        >
      </view>
      <view class="clerk-management-column-content">
        <view class="employee-card">
          <view class="employee-content">
            <view
              class="employee-list"
              v-for="(item, key) in employeeList"
              :key="key"
            >
              <view class="employee-list-info">
                <img src="#" class="employee-list-info-compile" />
                <view class="employee-info">
                  <view class="employee-info-name">
                    {{ item.name }}
                    <img
                      v-if="item.type == 0"
                      class="employee-identity-icon"
                      src="/static/images/shopkeeper-icon.png"
                    />
                    <img
                      v-if="item.type == 1"
                      class="employee-identity-icon"
                      src="/static/images/shopkeeper-icon.png"
                    />
                  </view>
                  <view class="employee-info-phone">{{ item.phone }}</view>
                </view>
              </view>
              <img
                v-if="item.status == 0"
                class="employee-list-info-operate-icon"
                src="/static/images/switch-close-icon.png"
                @click="changeState(key)"
              />
              <img
                v-if="item.status == 1"
                class="employee-list-info-operate-icon"
                src="/static/images/switch-open-icon.png"
                @click="changeState(key)"
              />
            </view>
          </view>
          <view class="add-btn">添加</view>
        </view>
      </view>
    </view>
    <!-- end clerk-management-column -->
  </view>
  <!-- end clerk-management -->
</template>

<script>
export default {
  data() {
    return {
      // 雇员列表
      employeeList: [
        {
          name: "李丽丽",
          type: 0,
          phone: "15688889999",
          status: 0,
        },
        {
          name: "李丽丽",
          type: 0,
          phone: "15688889999",
          status: 1,
        },
      ],
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
  methods: {
    // 更改雇员状态
    changeState(key) {
      this.employeeList[key].status == 1
        ? (this.employeeList[key].status = 0)
        : (this.employeeList[key].status = 1);
    },
  },
};
</script>

<style lang="less" scoped>
.clerk-management {
  padding: 0 30rpx;
  .clerk-management-column {
    .clerk-management-column-header {
      display: flex;
      justify-content: space-between;
      .clerk-management-column-title {
        font-size: 28rpx;
        font-weight: 500;
        color: #333333;
      }
      .clerk-management-column-subhead {
        font-size: 24rpx;
        font-weight: 500;
        color: #999999;
      }
    }
    .clerk-management-column-content {
      margin-top: 22rpx;
      .commission-card {
        width: 100%;
        padding: 20rpx 50rpx;
        box-sizing: border-box;
        background: rgba(220, 174, 98, 0.11);
        border-radius: 16rpx;
        border: 2rpx solid #ded0bb;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .commission-info {
          .commission-info-title {
            font-size: 28rpx;
            font-weight: 400;
            color: #333333;
            .commission-data {
              color: #c78125;
            }
          }
          .employee-data {
            font-size: 32rpx;
            font-weight: 500;
            color: #c78125;
          }
        }
        .commission-amend {
          font-size: 28rpx;
          font-weight: 500;
          color: #c78125;
        }
      }
      .employee-card {
        background: #ffffff;
        box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
        border-radius: 16rpx;
        padding: 0 50rpx;
        padding-bottom: 30rpx;
        .employee-content {
          .employee-list {
            padding: 16rpx 0;
            border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
            display: flex;
            align-items: center;
            justify-content: space-between;
            .employee-list-info {
              display: flex;
              .employee-list-info-compile {
                width: 30rpx;
                height: 30rpx;
              }
              .employee-info {
                margin-left: 22rpx;
                .employee-info-name {
                  font-size: 28rpx;
                  font-weight: 500;
                  color: #333333;
                  display: flex;
                  align-items: center;
                  .employee-identity-icon {
                    margin-left: 14rpx;
                    width: 60rpx;
                    height: 30rpx;
                  }
                }
                .employee-info-phone {
                  margin-top: 4rpx;
                  font-size: 24rpx;
                  font-weight: 400;
                  color: #999999;
                }
              }
            }
            .employee-list-info-operate-icon {
              width: 60rpx;
              height: 32rpx;
            }
          }
        }
        .add-btn {
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
  }
}
</style>
