<template>
  <Container>
    <!-- start bank-card -->
    <view class="bank-card m-t-10 justify-horizontal-center">
      <view class="bank-card-info">
        <label class="bank-card-info-label">银行卡</label>
        <text class="bank-card-info-bank-number">400 40000 40000 4000</text>
      </view>
      <img
        class="bank-card-info-operation"
        src="/static/images/right-icon.png"
      />
    </view>
    <!-- end bank-card -->
    <!-- start withdraw-card -->
    <view class="withdraw-card m-t-10">
      <view class="withdraw-card-name">提现金额</view>
      <view class="withdraw-card-import horizontal-center ">
        <view class="withdraw-card-import-symbol">￥</view>
        <input
          class="withdraw-card-import-input"
          type="text"
          placeholder="请输入提现金额"
        />
      </view>
      <view class="withdraw-balance">
        余额<text style="color: #333333">0.55元</text>
        <text style="color: #c78125; margin-left: 40rpx">全部提现</text>
      </view>
      <view class="next-step m-t-20 text-center">下一步</view>
    </view>
    <!-- end withdraw-card -->
    <view class="hint m-t-15 text-center">预计2小时内到账</view>
  </Container>
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
.bank-card {
  width: 100%;
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  border-radius: 16rpx;
  padding: 30rpx 48rpx 30rpx 32rpx;
  .bank-card-info {
    .bank-card-info-label {
      font-size: 28rpx;
      font-weight: 400;
      color: #333333;
    }
    .bank-card-info-bank-number {
      margin-left: 70rpx;
      font-size: 28rpx;
      font-weight: 500;
      color: #333333;
    }
  }
  .bank-card-info-operation {
    width: 17rpx;
    height: 22rpx;
  }
}
.withdraw-card {
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  border-radius: 16rpx;
  padding: 46rpx 30rpx 40rpx 30rpx;
  .withdraw-card-name {
    font-size: 28rpx;
    font-weight: 400;
    color: #333333;
  }
  .withdraw-card-import {
    margin-top: 24rpx;
    padding: 26rpx 0;
    border-bottom: 2rpx solid #f0f0f0;
    box-sizing: border-box;
    .withdraw-card-import-symbol {
      width: 82rpx;
      font-size: 48rpx;
      font-weight: 600;
      color: #333333;
    }
    .withdraw-card-import-input {
      font-size: 48rpx;
      font-weight: 400;
    }
  }
  .withdraw-balance {
    margin-top: 26rpx;
    font-size: 28rpx;
    font-weight: 400;
    color: #999999;
  }
  .next-step {
    width: 100%;
    padding: 18rpx 0;
    background: #c78125;
    border-radius: 16rpx;
    font-size: 32rpx;
    font-weight: 600;
    color: #ffffff;
  }
}
</style>
