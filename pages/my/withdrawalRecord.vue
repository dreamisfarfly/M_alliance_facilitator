<template>
  <Container>
    <!-- start withdrawal-record-list -->
    <view
      class="withdrawal-record-list m-t-10"
      v-for="(item, key) in withdrawalRecordList"
      :key="key"
    >
      <!-- start withdrawal-record-list-header -->
      <view class="withdrawal-record-list-header justify">
        <view class="withdrawal-record-list-header-info"
          >订号单：{{ item.orderNo }}</view
        >
        <view class="withdrawal-record-list-header-info">{{
          item.orderCreatedAt
        }}</view>
      </view>
      <!-- end withdrawal-record-list-header -->
      <!-- start withdrawal-record-list-content -->
      <view class="withdrawal-record-list-content">
        <view class="horizontal-center">
          <view class="withdrawal-record-info-name">提现金额</view>
          <view class="withdrawal-record-info-price m-l-15"
            >￥{{ item.withdrawalAmount }}</view
          >
        </view>
        <view class="justify-horizontal-center m-t-10">
          <view class="horizontal-center">
            <view class="withdrawal-record-info-name">实际到账</view>
            <view class="withdrawal-record-info-price m-l-15"
              >￥{{ item.actualAccount }}</view
            >
          </view>
          <view>
            <text class="withdrawal" v-if="item.status == 0">提现中</text>
            <text class="accomplish" v-if="item.status == 1">完成</text>
          </view>
        </view>
      </view>
      <!-- end withdrawal-record-list-content -->
    </view>
    <!-- end withdrawal-record-list -->
  </Container>
</template>

<script>
export default {
  data() {
    return {
      withdrawalRecordList: [
        {
          orderNo: "43268543252",
          orderCreatedAt: "2022-08-08 10:30",
          withdrawalAmount: 2000.0,
          actualAccount: 2000.0,
          status: 0,
        },
        {
          orderNo: "43268543252",
          orderCreatedAt: "2022-08-08 10:30",
          withdrawalAmount: 2000.0,
          actualAccount: 2000.0,
          status: 0,
        },
        {
          orderNo: "43268543252",
          orderCreatedAt: "2022-08-08 10:30",
          withdrawalAmount: 2000.0,
          actualAccount: 2000.0,
          status: 1,
        },
      ],
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
};
</script>

<style lang="less" scoped>
.withdrawal-record-list {
  padding: 0 30rpx;
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  border-radius: 16rpx;
  .withdrawal-record-list-header {
    padding: 20rpx 0 14rpx 0;
    border-bottom: 2rpx solid #f0f0f0;
    .withdrawal-record-list-header-info {
      font-size: 24rpx;
      font-weight: 400;
      color: #999999;
    }
  }
  .withdrawal-record-list-content {
    padding: 24rpx 0 22rpx 0;
    .withdrawal-record-info-name {
      font-size: 24rpx;
      font-weight: 400;
      color: #333333;
    }
    .withdrawal-record-info-price {
      font-size: 28rpx;
      font-weight: 600;
      color: #c78125;
    }
  }
}

.withdrawal {
  font-size: 24rpx;
  font-weight: 600;
  color: #60b251;
}

.accomplish {
  font-size: 24rpx;
  font-weight: 600;
  color: #999999;
}
</style>
