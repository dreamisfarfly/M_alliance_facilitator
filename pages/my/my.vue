<template>
  <!-- start 我的 -->
  <view>
    <!-- start my-header -->
    <view class="my-header">
      <!-- start my-header-user-info -->
      <view class="my-header-user-info">
        <!-- start user-info -->
        <view class="user-info">
          <img class="user-buddha" src="" />
          <view class="info">
            <view class="user-name-vessel">
              <text class="user-name">商户名丽丽</text>
              <img
                class="shopkeeper-icon"
                src="/static/images/shopkeeper-icon.png"
              />
            </view>
            <view class="user-account">账号：534536</view>
          </view>
        </view>
        <!-- end user-info -->
        <!-- start ewm-icon -->
        <img class="ewm-icon" src="/static/images/ewm-icon.png" />
        <!-- end ewm-icon -->
      </view>
      <!-- end my-header-user-info -->
    </view>
    <!-- end my-header -->
    <view class="my-content">
      <!-- start user-detailed -->
      <view class="user-detailed">
        <!-- start member-info -->
        <view class="member-info">
          <view class="member-info-list">
            <view class="member-info-list-count"
              >12<text class="unit">个</text></view
            >
            <view class="member-info-list-vip-name">门店会员</view>
          </view>
          <view class="separator"></view>
          <view class="member-info-list">
            <view class="member-info-list-count"
              >130<text class="unit">个</text></view
            >
            <view class="member-info-list-vip-name">所有会员</view>
          </view>
          <view class="separator"></view>
          <view class="member-info-list">
            <view class="member-info-list-count"
              >5<text class="unit">个</text></view
            >
            <view class="member-info-list-vip-name">直属会员</view>
          </view>
        </view>
        <!-- end member-info -->
        <!-- start commission -->
        <view class="commission">
          <view class="commission-info">
            <view class="commission-info-count">2000.00</view>
            <view class="commission-info-name">我的佣金</view>
          </view>
          <view class="commission-operation">
            <view
              class="withdrawal-record"
              @click="jump('/pages/my/withdrawalRecord')"
              >提现记录</view
            >
            <view class="to-withdrawal" @click="jump('/pages/my/withdraw')"
              >去提现</view
            >
          </view>
        </view>
        <!-- start commission -->
      </view>
      <!-- end user-detailed -->
      <Menu v-for="(item, key) in menuList" :key="key" :menu="item"></Menu>
    </view>
  </view>
  <!-- end 我的 -->
</template>

<script>
import Menu from "@/components/menu/menu.vue";
export default {
  data() {
    return {
      //进度 %
      scheduleCount: 20,
      // 菜单列表
      menuList: [
        {
          icon: "/static/images/commission-subsidiary-icon.png",
          name: "佣金明细",
          path: "/pages/my/commissionSubsidiary",
        },
        {
          icon: "/static/images/referral-code-icon.png",
          name: "推荐码",
          path: "/pages/my/referralCode",
        },
      ],
    };
  },
  mounted() {
    var a = document.getElementsByClassName("uni-page-head-hd")[0];
    a.style.opacity = 0;
  },
  methods: {
    // 跳转
    jump(path) {
      uni.navigateTo({
        url: path,
      });
    },
  },
  components: { Menu },
};
</script>

<style scoped lang="scss">
.my-header {
  width: 100%;
  height: 454rpx;
  background: url("/static/images/my-header-bak.png");
  background-size: 100% 100%;
  padding: 0 32rpx;
  padding-top: 86rpx;
  box-sizing: border-box;
  .my-header-user-info {
    display: flex;
    align-items: center;
    justify-content: space-between;
    .user-info {
      display: flex;
      .user-buddha {
        width: 136rpx;
        height: 136rpx;
        border-radius: 50% 50%;
      }
      .info {
        margin-left: 22rpx;
        .user-name-vessel {
          margin-top: 12rpx;
          display: flex;
          align-items: center;
          .user-name {
            font-size: 32rpx;
            font-weight: 500;
            color: #ffffff;
          }
          .shopkeeper-icon {
            margin-left: 20rpx;
            width: 60rpx;
            height: 30rpx;
          }
        }
        .user-account {
          margin-top: 12rpx;
          font-size: 24rpx;
          font-weight: 400;
          color: #ffffff;
        }
      }
    }
    .ewm-icon {
      width: 50rpx;
      height: 50rpx;
      margin-right: 16rpx;
    }
  }
}

.my-content {
  position: relative;
  top: -160rpx;
  width: 100%;
  padding: 0 30rpx;
  box-sizing: border-box;
  .user-detailed {
    width: 100%;
    background: #ffffff;
    box-shadow: 0 -10rpx 12rpx 0 rgba(0, 0, 0, 0.05);
    border-radius: 16rpx;
    padding: 20rpx;
    padding-top: 0rpx;
    box-sizing: border-box;
    .member-info {
      display: flex;
      align-items: center;
      .member-info-list {
        flex: 1;
        display: flex;
        align-items: center;
        flex-direction: column;
        padding: 40rpx 0;
        .member-info-list-count {
          font-size: 40rpx;
          font-weight: 600;
          color: #333333;
          .unit {
            font-size: 24rpx;
          }
        }
        .member-info-list-vip-name {
          margin-top: 10rpx;
          font-size: 24rpx;
          font-weight: 400;
          color: #999999;
        }
      }
    }
    .commission {
      width: 100%;
      background: rgba(220, 174, 98, 0.11);
      border-radius: 16rpx;
      border: 2rpx solid #ded0bb;
      padding: 14rpx 24rpx 18rpx 26rpx;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      .commission-info {
        .commission-info-count {
          font-size: 48rpx;
          font-weight: 600;
          color: #333333;
        }
        .commission-info-name {
          font-size: 20rpx;
          font-weight: 500;
          color: #999999;
        }
      }
      .commission-operation {
        display: flex;
        padding-top: 24rpx;
        .withdrawal-record {
          width: 128rpx;
          height: 50rpx;
          border-radius: 8rpx;
          border: 2rpx solid #c78125;
          font-size: 24rpx;
          font-weight: 500;
          color: #c78125;
          text-align: center;
          line-height: 50rpx;
        }
        .to-withdrawal {
          margin-left: 20rpx;
          width: 120rpx;
          height: 50rpx;
          background: #c78125;
          border-radius: 8rpx;
          border: 2rpx solid #c78125;
          font-size: 24rpx;
          font-weight: 500;
          color: #ffffff;
          text-align: center;
          line-height: 50rpx;
        }
      }
    }
  }
}

.separator {
  width: 2rpx;
  height: 110rpx;
  opacity: 0.05;
  background: #000000;
}
</style>
