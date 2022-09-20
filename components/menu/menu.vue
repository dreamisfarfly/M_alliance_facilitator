<template>
  <!-- start 菜单 -->
  <view class="menu" @click="jump(menu.path)">
    <view class="menu-info">
      <img class="menu-info-icon" :src="menu.icon" />
      <text class="menu-info-name">{{ menu.name }}</text>
    </view>
    <img class="menu-operation" src="/static/images/right-icon.png" />
  </view>
  <!-- end 菜单 -->
</template>

<script>
export default {
  props: {
    // 菜单
    menu: {
      typeof: Object,
      default: function () {
        return {};
      },
    },
  },
  methods: {
    // 跳转
    jump(path) {
      uni.navigateTo({
        url: path,
      });
    },
  },
};
</script>

<style lang="less" scoped>
.menu {
  background: #ffffff;
  box-shadow: 0 8rpx 16rpx 0 rgba(108, 119, 128, 0.05);
  border-radius: 16rpx;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 22rpx 46rpx 22rpx 30rpx;
  box-sizing: border-box;
  margin-top: 20rpx;
  .menu-info {
    display: flex;
    align-items: center;
    .menu-info-icon {
      width: 56rpx;
      height: 56rpx;
    }
    .menu-info-name {
      margin-left: 20rpx;
      font-size: 28rpx;
      font-weight: 400;
      color: #333333;
    }
  }
  .menu-operation {
    width: 10rpx;
    height: 18rpx;
  }
}
</style>
