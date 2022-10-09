<template>
  <!-- start 店铺管理 -->
  <view>
    <!-- start 导航栏 -->
    <u-navbar
      :is-back="false"
      title="店铺管理"
      :background="background"
      title-color="#333333"
      title-size="32"
      :title-bold="true"
    >
      <template slot="right">
        <text
          class="release-message"
          @click="jump('/pages/shopManagement/perfectInformation')"
          >添加</text
        >
      </template>
    </u-navbar>
    <!-- end 导航栏 -->
    <!-- start search-vessel -->
    <view class="search-vessel" ref="searchVessel">
      <search
        v-model="searchValue"
        @searchFun="searchFun"
        placeholder="搜索"
      ></search>
    </view>
    <!-- end search-vessel -->
    <!-- start screen-vessel -->
    <view class="screen-vessel">
      <!-- start screen-vessel-menu -->
      <view class="screen-vessel-menu">
        <!-- start screen-vessel-menu-list -->
        <view
          class="screen-vessel-menu-list"
          v-for="(item, key) in menuList"
          :class="selectIndex == key ? 'select-screen-vessel-menu-list' : ''"
          @click="selectMenu(key)"
          :key="key"
          >{{ item.name }}</view
        >
        <!-- end screen-vessel-menu-list -->
      </view>
      <!-- end screen-vessel-menu -->
      <!-- start screen-vessel-content -->
      <view class="screen-vessel-content">
        <view class="screen-vessel-content-title">店铺总数：11个</view>
        <view class="shop-content">
          <!-- start shop-list -->
          <view class="shop-list" v-for="(item, key) in shopList" :key="key">
            <view class="shop-list-info">
              <img src="" class="shop-list-info-icon" />
              <view class="shop-info">
                <view class="shop-name">长沙山水健康体检中心</view>
                <view class="shop-discounts"
                  >门店通用折扣：<text class="yellow-font">8折</text></view
                >
                <view class="shop-member-price"
                  >会员：<text class="yellow-font">180</text></view
                >
              </view>
            </view>
            <view class="shop-list-operation">
              <view class="shop-list-at">店铺有效期：2023-06-10</view>
              <img
                v-if="item.status == 0"
                @click="changeShopStatus(key)"
                src="/static/images/switch-close-icon.png"
                class="switch-btn"
              />
              <img
                v-if="item.status == 1"
                @click="changeShopStatus(key)"
                src="/static/images/switch-open-icon.png"
                class="switch-btn"
              />
            </view>
          </view>
          <!-- end shop-list -->
        </view>
      </view>
      <!-- end screen-vessel-content -->
    </view>
    <!-- end screen-vessel -->
  </view>
  <!-- end 店铺管理 -->
</template>

<script>
import search from "@/components/search/search.vue";
export default {
  components: { search },
  data() {
    return {
      // 导航栏背景
      background: {
        backgroundColor: "#FFFFFF",
      },
      // 搜索值
      searchValue: null,
      // 菜单列表
      menuList: [
        {
          name: "全部",
        },
        {
          name: "餐饮",
        },
        {
          name: "住宿",
        },
        {
          name: "生活",
        },
        {
          name: "医疗",
        },
        {
          name: "美食",
        },
        {
          name: "酒吧",
        },
      ],
      // 选中索引
      selectIndex: 0,
      // 店铺列表
      shopList: [
        {
          status: 0,
        },
        {
          status: 1,
        },
      ],
    };
  },
  methods: {
    // 搜索
    searchFun() {
      console.log(this.searchValue);
    },
    // 选中菜单
    selectMenu(key) {
      this.selectIndex = key;
    },
    // 更改店铺状态
    changeShopStatus(key) {
      this.shopList[key].status == 0
        ? (this.shopList[key].status = 1)
        : (this.shopList[key].status = 0);
    },
    // 添加店铺
    jump(path) {
      uni.navigateTo({
        url: path,
      });
    },
  },
};
</script>

<style lang="less" scoped>
.release-message {
  margin-right: 50rpx;
  font-size: 32rpx;
  font-weight: 500;
  color: #c78125;
}

.search-vessel {
  background: #f9f9f9;
  padding: 16rpx 30rpx;
  box-sizing: border-box;
  position: fixed;
  width: 100%;
  top: 88rpx;
}

.screen-vessel {
  margin-top: 100rpx;
  display: flex;
  height: 100vh;
  .screen-vessel-menu {
    width: 160rpx;
    background: #efefef;
    box-shadow: inset 0 -2rpx 0 0 rgba(229, 229, 229, 0.5);
    .screen-vessel-menu-list {
      width: 100%;
      height: 80rpx;
      text-align: center;
      line-height: 80rpx;
      font-size: 28rpx;
      font-weight: 400;
      color: #333333;
    }
    .select-screen-vessel-menu-list {
      font-weight: 500;
      background: #ffffff;
      color: #c78125;
    }
  }
  .screen-vessel-content {
    flex: 1;
    background: #ffffff;
    padding: 0 30rpx;
    .screen-vessel-content-title {
      margin-top: 36rpx;
      font-size: 32rpx;
      font-weight: 500;
      color: #333333;
    }
    .shop-content {
      .shop-list {
        padding: 32rpx 0 24rpx 0;
        box-sizing: border-box;
        border-bottom: 2rpx solid rgba(0, 0, 0, 0.05);
        .shop-list-info {
          display: flex;
          .shop-list-info-icon {
            width: 120rpx;
            height: 120rpx;
          }
          .shop-info {
            margin-left: 20rpx;
            .shop-name {
              font-size: 32rpx;
              font-weight: 500;
              color: #333333;
              line-height: 44rpx;
            }
            .shop-discounts {
              margin-top: 10rpx;
              font-size: 24rpx;
              font-weight: 400;
              color: #999999;
              line-height: 34rpx;
            }
            .shop-member-price {
              margin-top: 8rpx;
              font-size: 12px;
              font-weight: 400;
              color: #999999;
              line-height: 34rpx;
            }
          }
        }
        .shop-list-operation {
          margin-top: 30rpx;
          display: flex;
          align-items: center;
          justify-content: space-between;
          .shop-list-at {
            font-size: 24rpx;
            font-weight: 400;
            color: #666666;
          }
          .switch-btn {
            width: 60rpx;
            height: 32rpx;
          }
        }
      }
    }
  }
}

.yellow-font {
  color: #c78125;
}
</style>
