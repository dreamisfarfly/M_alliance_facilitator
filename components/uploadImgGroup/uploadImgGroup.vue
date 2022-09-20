<template>
  <!-- start upload-img-group -->
  <view class="upload-img-group">
    <template v-if="imgList.length != 0">
      <view
        class="upload-list"
        v-for="(item,key) in imgList" :key="key"
        :class="maxCount > key ? 'upload-list-right' : ''"
      >
        <img class="upload-list-icon" src="/static/images/add-icon.png" />
        <img class="del-img" src="/static/images/del-img-icon.png" />
      </view>
    </template>
    <u-upload
      :custom-btn="true"
      ref="uUpload"
      :action="action"
      v-if="imgList.length != maxCount"
    >
      <view slot="addBtn" class="add-btn">
        <img class="add-btn-icon" src="/static/images/add-icon.png" />
      </view>
    </u-upload>
  </view>
  <!-- end upload-img-group -->
</template>

<script>
export default {
  data() {
    return {
      // 地址
      action: "",
      // 图片list
      imgList: [{},{}],
    };
  },
  props: {
    // 图片最大数量
    maxCount: {
      typeof: Number,
      default: 3,
    },
  },
};
</script>

<style lang="less" scoped>
.upload-img-group {
  display: flex;
  .upload-list-right {
    margin-right: 20rpx;
  }
  .upload-list {
    width: 184rpx;
    height: 138rpx;
    position: relative;
    .upload-list-icon {
      width: 100%;
      height: 100%;
      border-radius: 16rpx;
    }
    .del-img {
      position: absolute;
      top: 6rpx;
      right: 6rpx;
      width: 32rpx;
      height: 32rpx;
      z-index: 996;
    }
  }
  .add-btn {
    width: 184rpx;
    height: 138rpx;
    .add-btn-icon {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
