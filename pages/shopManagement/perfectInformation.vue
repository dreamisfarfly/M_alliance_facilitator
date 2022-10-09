<template>
  <view>
    <!-- start 导航栏 -->
    <u-navbar
      :is-back="false"
      title="添加店铺"
      :background="background"
      title-color="#333333"
      title-size="32"
      :title-bold="true"
    >
      <template slot="right">
        <text class="shop-data"
          ><text style="color: #c78125">11</text>/100</text
        >
      </template>
    </u-navbar>
    <!-- end 导航栏 -->
    <!-- start perfect-information -->
    <view class="perfect-information">
      <!-- start perfect-information-card -->
      <view class="perfect-information-card">
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label">门店类型</view>
          <view class="column-list-content justify-align">
            <text class="column-list-val">餐饮</text>
            <img src="/static/images/right-icon.png" class="operation-icon" />
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label"
            ><text class="required">*</text>门店名称</view
          >
          <view class="column-list-content justify-align">
            <input class="column-list-val" placeholder="请输入门店名称" />
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label"
            ><text class="required">*</text>负责人姓名</view
          >
          <view class="column-list-content justify-align">
            <input class="column-list-val" placeholder="请输入负责人姓名" />
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label"
            ><text class="required">*</text>负责人电话</view
          >
          <view class="column-list-content justify-align">
            <input class="column-list-val" placeholder="请输入负责人电话" />
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label">门店地址</view>
          <view class="column-list-content justify-align">
            <text class="column-list-val">洞井路1239号</text>
            <img src="/static/images/right-icon.png" class="operation-icon" />
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label">营业时间</view>
          <view class="column-list-content">
            <view class="column-list-val">工作日：8:00 -18:00</view>
            <view class="column-list-val">周六周日：8:00 -28:00</view>
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label">付费类型</view>
          <view class="column-list-content justify-align">
            <text class="column-list-val">月卡</text>
            <img src="/static/images/right-icon.png" class="operation-icon" />
          </view>
        </view>
        <!-- end column-list -->
        <!-- start column-list -->
        <view class="column-list">
          <view class="column-list-label">有效期</view>
          <view class="column-list-content justify-align">
            <text class="column-list-val">2022-09-09 - 2022-10</text>
          </view>
        </view>
        <!-- end column-list -->
        <!-- start img-group -->
        <view class="img-group">
          <view class="img-group-name">门店图片</view>
          <view class="img-group-content">
            <UploadImgGroup />
          </view>
        </view>
        <!-- end img-group -->
        <!-- start img-group -->
        <view class="img-group">
          <view class="img-group-name">门店环境</view>
          <view class="img-group-content">
            <UploadImgGroup />
          </view>
        </view>
        <!-- end img-group -->
        <!-- start img-group -->
        <view class="img-group">
          <view class="img-group-name">营业执照</view>
          <view class="img-group-content">
            <UploadImgGroup />
          </view>
        </view>
        <!-- end img-group -->
        <!-- start confirm-btn -->
        <view class="confirm-btn">确定</view>
        <!-- end confirm-btn -->
      </view>
      <!-- end perfect-information-card -->
    </view>
    <!-- end perfect-information -->
  </view>
</template>

<script>
import UploadImgGroup from "@/components/uploadImgGroup/uploadImgGroup.vue";
export default {
  data() {
    return {
      // 导航栏背景
      background: {
        backgroundColor: "#FFFFFF",
      },
    };
  },
  components: { UploadImgGroup },
};
</script>

<style lang="less" scoped>
.perfect-information {
  padding: 20rpx 30rpx 20rpx 30rpx;
  .perfect-information-card {
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
}

.img-group {
  margin-top: 38rpx;
  .img-group-name {
    font-weight: 400;
    color: #999999;
    font-size: 24rpx;
  }
  .img-group-content {
    margin-top: 36rpx;
  }
}

.column-list {
  display: flex;
  justify-content: space-between;
  box-sizing: border-box;
  padding: 36rpx 0;
  border-bottom: 2rpx solid rgba(0, 0, 0, 0.1);
  .column-list-label {
    width: 202rpx;
    display: flex;
    align-items: center;
    .required {
      margin-right: 14rpx;
      font-size: 24rpx;
      font-weight: 400;
      color: #ff0000;
    }
  }
  .column-list-content {
    flex: 1;
    .column-list-val {
      font-size: 28rpx;
      font-weight: 500;
      color: #333333;
    }
    .operation-icon {
      width: 12rpx;
      height: 20rpx;
    }
  }
  .justify-align {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
}

.shop-data {
  margin-right: 34rpx;
  font-size: 32rpx;
  font-weight: 500;
  color: #333333;
}
</style>
