<template>
    <view class="s-loading"
          :style="{height:size+'px',width:size+'px'}"
    >
        <svg
            :width="size"
            :height="size"
            viewBox="25 25 50 50"
            class="s-loading__svg"
        >
            <circle
                cx="50"
                cy="50"
                r="20"
                fill="none"
                :stroke-width="3"
                :style="{ color: innerColor}"
            ></circle>
        </svg>

        <!-- #ifdef MP -->
         <view class="s-loading__mp" :style="{ color: innerColor}"> </view>
        <!-- #endif -->

        <!-- #ifdef APP -->
<!--         <view class="s-loading__app" :style="{ color: innerColor}"> </view>-->
        <!-- #endif -->
    </view>
</template>

<script>
    export default {
        name:'SunnyLoading',
        props:{
            color:String,
            size:{ type:Number, default:25 }
        },
        computed:{
            innerColor(){ return this.color || "409EFF" }
        }
    };
</script>

<style scoped lang="scss">
    .s-loading{
        display: inline-block;
        line-height: 1;
        border: 1px solid red;


        @keyframes loading-rotate {
            0% { transform: rotate(0); }
            100% { transform: rotate(360deg); }
        }

        @keyframes loading-dash {
            0% { stroke-dasharray: 1, 200; stroke-dashoffset: 0; }
            50% { stroke-dasharray: 90, 150; stroke-dashoffset: -40; }
            100% { stroke-dasharray: 90, 150; stroke-dashoffset: -120; }
        }

        &__svg {
            animation: loading-rotate 2s linear infinite;
            transform-origin: center center;

            circle {
                display: inline-block;
                animation: loading-dash 1.5s ease-in-out infinite;
                stroke: currentColor;
                stroke-linecap: round;
            }
        }

        &__mp,
        &__app {
            height: 100%;
            width: 100%;
            border-radius: 100%;
            border: 4rpx solid rgba(0, 0, 0, 0.1);
            border-bottom: 4rpx solid currentColor;
            box-sizing: border-box;
            animation: loading-rotate 1s linear infinite;
            position: relative;
        }

    }


</style>
