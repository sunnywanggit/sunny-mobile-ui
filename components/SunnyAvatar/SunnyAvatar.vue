<template>
    <view :class="['s-avatar', isShape]" :style="{ height, width }">

        <slot v-if="!src">
            <text  :style="{ fontSize }"></text>
        </slot>

        <image
                class="s-avatar__target"
                v-else
                :src="src"
        ></image>
    </view>
</template>

<script>
    export default {
        name:"SunnyAvatar",
        props: {
            src: String,
            size: { type: Number, default: 80 },
            shape: { type: String, default: 'circle' }
        },
        computed: {
            isShape() { return `s-avatar--${this.shape}`; },

            height() { return this.size + 'rpx'; },

            width() { return this.size + 'rpx'; },

            fontSize() { return this.size / 1.7 + 'rpx'; }
        },
    };
</script>
<style lang="scss">
    .s-avatar {
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #c0c4cc;
        font-size: 28rpx;
        color: #fff;
        overflow: hidden;
        box-sizing: border-box;

        &--circle {
             border-radius: 100%;
         }

        &--square {
             border-radius: 10rpx;
         }

        &__target {
             height: 100%;
             width: 100%;
         }
    }
</style>
