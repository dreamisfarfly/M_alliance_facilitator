<template>
  <!-- start withdraw -->
  <view class="withdraw">
    <!-- start bank-card -->
    <view class="bank-card">
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
    <view class="withdraw-card">
      <view class="withdraw-card-name">提现金额</view>
      <view class="withdraw-card-import">
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
      <view class="next-step">下一步</view>
    </view>
    <!-- end withdraw-card -->
    <view class="withdraw-hint">预计2小时内到账</view>
  </view>
  <!-- end withdraw -->
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
.withdraw {
  padding: 0 30rpx;
  padding-top: 20rpx;
  .bank-card {
    width: 100%;
    box-sizing: border-box;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 30rpx 48rpx 30rpx 32rpx;
    display: flex;
    justify-content: space-between;
    align-items: center;
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
    margin-top: 20rpx;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    padding: 46rpx 30rpx 40rpx 30rpx;
    box-sizing: border-box;
    .withdraw-card-name {
      font-size: 28rpx;
      font-weight: 400;
      color: #333333;
    }
    .withdraw-card-import {
      margin-top: 24rpx;
      padding: 26rpx 0;
      display: flex;
      align-items: center;
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
      margin-top: 40rpx;
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
  .withdraw-hint {
    margin-top: 30rpx;
    text-align: center;
    font-size: 24rpx;
    font-weight: 400;
    color: #999999;
  }
}
</style>
