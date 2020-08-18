<template>
    <view class="demo-avatar">
        <SunnyCard label="头像形状">
            <SunnyRow type="flex">
                <SunnyAvatar :src="url"></SunnyAvatar>
                <SunnyAvatar :src="url" shape="square"></SunnyAvatar>
            </SunnyRow>
        </SunnyCard>

        <SunnyCard label="头像大小">
            <SunnyRow type="flex">
                <SunnyAvatar :src="url" :size="70"></SunnyAvatar>

                <SunnyAvatar :src="url" :size="80"></SunnyAvatar>

                <SunnyAvatar :src="url" :size="90"></SunnyAvatar>

                <SunnyAvatar :src="url" :size="100"></SunnyAvatar>
            </SunnyRow>
        </SunnyCard>
    </view>
</template>

<script>
    import SunnyCard from '../../components/SunnyCard/SunnyCard';
    import SunnyRow from '../../components/SunnyRow/SunnyRow';
    import SunnyAvatar from '../../components/SunnyAvatar/SunnyAvatar';
    export default {
        components: {SunnyAvatar, SunnyRow, SunnyCard},
        data() {
            return {
                url:'https://s1.ax1x.com/2020/07/31/aQO84s.png',
            };
        }
    };
</script>

<style lang="scss">
    .demo-avatar {
        .s-row {
            .s-avatar {
                margin: 0 20rpx;
            }
        }
    }
</style>
