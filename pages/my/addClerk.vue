<template>
  <!-- start add-clerk -->
  <view class="add-clerk">
    <!-- start add-clerk-card -->
    <view class="add-clerk-card">
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-name">员工姓名</view>
        <view class="column-list-operation">
          <input
            class="column-list-operation-input"
            placeholder="10个字符以内"
            v-model="form.name"
          />
        </view>
      </view>
      <!-- end column-list -->
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-name">性别</view>
        <view class="column-list-operation" @click="sexOpen=true">
          {{ form.sex == 0 ? "男" : "女" }} >
        </view>
      </view>
      <!-- end column-list -->
      <!-- start column-list -->
      <view class="column-list">
        <view class="column-list-name">手机号</view>
        <view class="column-list-operation">
          <input
            class="column-list-operation-input"
            placeholder="请输入11位手机号"
            v-model="form.phone"
          />
        </view>
      </view>
      <!-- end column-list -->
      <!-- start confirm-btn -->
      <view class="confirm-btn">确定</view>
      <!-- end confirm-btn -->
    </view>
    <!-- end add-clerk-card -->
    <!-- start card-hint -->
    <view class="card-hint">
      账号为手机号码，初始密码8888888。登录后请及时修改密码。</view
    >
    <!-- end card-hint -->
    <!-- start 选择器 -->
    <u-select v-model="sexOpen" :list="sexList" @confirm="confirmSex"></u-select>
    <!-- end 选择器 -->
  </view>
  <!-- end add-clerk -->
</template>

<script>
export default {
  data() {
    return {
      // 性别选择器是否开启
      sexOpen: false,
      // 表单
      form: {
        name: null,
        sex: 0,
        phone: null,
      },
      // 性别选择器
      sexList: [
        {
          value: 0,
          label: "男",
        },
        {
          value: 1,
          label: "女",
        },
      ],
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
  methods: {
    // 选择性别
    confirmSex(event){
        this.form.sex = event[0].value
    }
  }
};
</script>

<style lang="less" scoped>
.add-clerk {
  padding: 20rpx 30rpx 0 30rpx;
  .add-clerk-card {
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 0 50rpx;
    padding-bottom: 40rpx;
    .confirm-btn {
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
  .card-hint {
    margin-top: 20rpx;
    font-size: 24rpx;
    font-weight: 400;
    color: #666666;
  }
}

.column-list {
  display: flex;
  justify-content: space-between;
  box-sizing: border-box;
  padding: 36rpx 0;
  border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
  .column-list-name {
    font-size: 24rpx;
    font-weight: 400;
    color: #999999;
  }
  .column-list-operation {
    display: flex;
    align-items: center;
    font-size: 28rpx;
    font-weight: 500;
    color: #333333;
    .column-list-operation-input {
      text-align: right;
      align-items: center;
      font-size: 28rpx;
      font-weight: 500;
      color: #333333;
    }
  }
}
</style>
