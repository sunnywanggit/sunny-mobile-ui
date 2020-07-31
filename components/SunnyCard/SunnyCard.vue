<template>
    <view class="s-card">
        <view class="s-card__header" v-if="label || $slots.header">
            <text class="s-card__label">{{ label }}</text>
        </view>
        <view class="s-card__container" :style="{ padding }">
            <slot></slot>
        </view>
        <view class="s-card__footer" v-if="$slots.footer"></view>
    </view>
</template>

<script>
    export default {
        name:'SunnyCard',
        props: {
            label: String,
            padding: {
                type: String,
                default: '20rpx'
            }
        }
    };
</script>
<style lang="scss">
.s-card {

    &__header {
        display: flex;
        align-items: center;
        padding: 10rpx 20rpx 10rpx 24rpx;
        height: 60rpx;
        position: relative;

        &::before {
            content: '';
            display: inline-block;
            height: 6rpx;
            width: 6rpx;
            background-color: $color-primary;
            position: absolute;
            left: 8rpx;
            border-top-right-radius: 10rpx;
            border-bottom-right-radius: 10rpx;
        }
    }

    &__label {
        font-size: 26rpx;
        color: #909ca2;
    }

    &__container {
        background-color: #fff;
    }

    &__footer {
        border-top: 1rpx solid #eee;
        padding: 10rpx;
    }
}
</style>
