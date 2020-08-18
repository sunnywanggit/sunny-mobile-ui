<template>
    <view class="s-rate">
        <view class="s-rate__icon" v-for="(item, index) in list" :key="index">
            <SunnyIcon :name="icon" :size="size" :color="voidColor"/>

            <view
                    class="s-rate__icon-active"
                    :style="{
					width: item.width
				}"
            >
                <SunnyIcon :name="icon" :size="size" :color="item.color"/>
            </view>
        </view>
    </view>
</template>

<script>

    import {getCurrentColor} from '../../util/util';
    import SunnyIcon from '../SunnyIcon/SunnyIcon';

    export default {
        name:'SunnyRate',
        components: {SunnyIcon},
        props: {
            icon: { type: String, default: 's-icon-favor-fill' },
            color: { type: [String, Array], default: '#409EFF' },
            voidColor: { type: String, default: '#C6D1DE' },
            size: { type: [Number, String], default: 40 },
            value: { type: [Number, String], default: 0 },
            max: { type: [Number, String], default: 5 },
        },
        data() {
            return { value2: 0 };
        },
        watch: {
            value: {
                immediate: true,
                handler(val) {
                    this.value2 = val;
                }
            }
        },
        computed: {
            list() {
                return new Array(this.max).fill(1).map((e, i) => {
                    let int = parseInt(this.value2);
                    let dec = this.value2 - int;

                    return {
                        width: (this.value2 > i ? (int > i ? 100 : dec * 100) : 0) + '%',
                        color: getCurrentColor({
                            value: this.value2,
                            color: this.color,
                            max: this.max
                        })
                    };
                });
            }
        },
    };
</script>

<style lang="scss" scoped>
    .s-rate {
        display: flex;
        align-items: center;

        &__icon {
            position: relative;
            margin-right: 10rpx;
        }

        &__icon-active {
            position: absolute;
            top: 0;
            left: 0;
            overflow: hidden;
        }

        &__text {
            font-size: 26rpx;
            margin-left: 10rpx;
        }
    }
</style>
