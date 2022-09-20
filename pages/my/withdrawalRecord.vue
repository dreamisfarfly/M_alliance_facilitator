<template>
  <!-- start withdrawal-record -->
  <view class="withdrawal-record">
    <!-- start withdrawal-record-list -->
    <view
      class="withdrawal-record-list"
      v-for="(item, key) in withdrawalRecordList"
      :key="key"
    >
      <!-- start withdrawal-record-list-header -->
      <view class="withdrawal-record-list-header">
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
        <view class="withdrawal-record-info">
          <view class="withdrawal-record-info-name">提现金额</view>
          <view class="withdrawal-record-info-price"
            >￥{{ item.withdrawalAmount }}</view
          >
        </view>
        <view class="withdrawal-info">
          <view class="withdrawal-record-info">
            <view class="withdrawal-record-info-name">实际到账</view>
            <view class="withdrawal-record-info-price"
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
  </view>
  <!-- end withdrawal-record -->
</template>

<script>
export default {
  data() {
    return {
      withdrawalRecordList: [
        {
          orderNo: "43268543252",
          orderCreatedAt: "2022-08-08 10：30",
          withdrawalAmount: 2000.0,
          actualAccount: 2000.0,
          status: 0,
        },
        {
          orderNo: "43268543252",
          orderCreatedAt: "2022-08-08 10：30",
          withdrawalAmount: 2000.0,
          actualAccount: 2000.0,
          status: 0,
        },
        {
          orderNo: "43268543252",
          orderCreatedAt: "2022-08-08 10：30",
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
.withdrawal-record {
  padding: 0 30rpx;
  .withdrawal-record-list {
    margin-top: 20rpx;
    padding: 0 30rpx;
    box-sizing: border-box;
    background: #ffffff;
    box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
    border-radius: 16rpx;
    .withdrawal-record-list-header {
      padding: 20rpx 0 14rpx 0;
      border-bottom: 2rpx solid #f0f0f0;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      .withdrawal-record-list-header-info {
        font-size: 24rpx;
        font-weight: 400;
        color: #999999;
      }
    }
    .withdrawal-record-list-content {
      padding: 24rpx 0 22rpx 0;
      .withdrawal-record-info {
        display: flex;
        align-items: center;
        .withdrawal-record-info-name {
          font-size: 24rpx;
          font-weight: 400;
          color: #333333;
        }
        .withdrawal-record-info-price {
          margin-left: 30rpx;
          font-size: 28rpx;
          font-weight: 600;
          color: #c78125;
        }
      }
      .withdrawal-info {
        width: 100%;
        margin-top: 20rpx;
        display: flex;
        align-items: center;
        justify-content: space-between;
      }
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
