<template>
  <Container>
    <!-- start commission-subsidiary-list -->
    <view
      class="commission-subsidiary-list"
      v-for="(item, key) in 6"
      :key="key"
    >
      <view class="justify-horizontal-center">
        <view class="cost-info-title">直属会员卡年费</view>
        <view class="cost-info-title">+2000元</view>
      </view>
      <view class="justify-horizontal-center m-t-10">
        <view class="entry-info-time">2022年5月17日 16:43:01</view>
        <view class="commission-btn already-recorded">已入账</view>
      </view>
    </view>
    <!-- end commission-subsidiary-list -->
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
.commission-subsidiary-list {
  padding: 24rpx 30rpx 20rpx 30rpx;
  box-sizing: border-box;
  width: 100%;
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  border-radius: 16rpx;
  margin-top: 20rpx;
  .cost-info-title {
    font-size: 28rpx;
    font-weight: 550;
    color: #333333;
    line-height: 40rpx;
  }
  .entry-info-time {
    font-size: 24rpx;
    font-weight: 400;
    color: #999999;
    line-height: 34rpx;
  }
  .commission-btn {
    padding: 8rpx 16rpx;
    border-radius: 8rpx;
    font-size: 20rpx;
    display: flex;
    justify-content: center;
  }
  .already-recorded {
    border: 2rpx solid #60b251;
    color: #60b251;
  }
}
</style>
