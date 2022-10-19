<template>
    <!-- start 容器 -->
    <view class="container">
        <slot></slot>
    </view>
    <!-- end 容器 -->
</template>

<script>
export default {
    
}
</script>

<style lang="less" scoped>
.container{
    padding: 0 20rpx;
    box-sizing: border-box;
}
</style>