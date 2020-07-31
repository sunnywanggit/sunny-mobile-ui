<template>
    <view class="container">
        <view class="item">
            <view class="item-header">
                按钮形状
            </view>
            <view class="item-body">
                <SunnyButton >默认</SunnyButton>
                <SunnyButton :round="true">圆角</SunnyButton>
            </view>
        </view>

        <view class="item">
            <view class="item-header">
                按钮尺寸
            </view>
            <view class="item-body">
                <SunnyButton size="small" :round="true">小尺寸</SunnyButton>
                <SunnyButton size="normal" :round="true">默认</SunnyButton>
                <SunnyButton size="large" :round="true">大尺寸</SunnyButton>
            </view>
        </view>

        <view class="item">
            <view class="item-header">
                按钮颜色
            </view>
            <view class="item-body">
                <SunnyButton :round="true" color="#eb4344">嫣红</SunnyButton>
            </view>
        </view>
    </view>
</template>

<script>
    import SunnyButton from '../../components/SunnyButton/SunnyButton';
    import scopeClassMaker from '../../helper/classes';
    const scopedClass  =scopeClassMaker('button-demo');
    export default {
        components:{
            SunnyButton
        },
        onLoad(){
        },
        methods:{
            sc(classSuffix){
                console.log(scopedClass(classSuffix));
                return scopedClass(classSuffix);
            }
        }
    };
</script>

<style lang="scss">
    @import "./button";
</style>
