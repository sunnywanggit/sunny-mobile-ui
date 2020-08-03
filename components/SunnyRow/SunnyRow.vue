<template>
    <view
            :class="['s-row', classList]"
            :style="{ marginLeft, marginRight, backgroundColor }"
    >
        <slot></slot>
    </view>
</template>

<script>
    export default {
        name: "SunnyRow",
        props: {
            gutter: [Number, String],
            type: String,
            justify: { type: String, default: "start" },
            align: { type: String, default: "top" },
            backColor:{ type:String, default:'transparent' },
            wrap: Boolean
        },
        computed: {
            classList() {
                let list = [];

                if (this.justify !== "start") {
                    list.push(`is-justify-${this.justify}`);
                }

                if (this.align !== "top") {
                    list.push(`is-align-${this.align}`);
                }

                if (this.wrap) {
                    list.push("is-wrap");
                }

                switch (this.type) {
                    default:
                        list.push(`s-row--${this.type}`);
                }

                return list;
            },
            marginLeft() { return `-${this.gutter / 2}rpx`; },
            marginRight() { return this.marginLeft; },
            backgroundColor(){ return this.backColor }
        }
    };
</script>
<style lang="scss">
.s-row {
    position: relative;
    box-sizing: border-box;


    &::after,
    &::before {
        content: "";
        display: table;
    }

    &::after {
        clear: both;
    }

    &--flex {
        display: flex;

        &::after,
        &::before {
            display: none;
        }
    }

    &.is-justify-center {
        justify-content: center;
    }

    &.is-justify-end {
        justify-content: flex-end;
    }

    &.is-justify-space-between {
        justify-content: space-between;
    }

    &.is-justify-space-around {
        justify-content: space-around;
    }

    &.is-align-middle {
        align-items: center;
    }

    &.is-align-bottom {
        align-items: flex-end;
    }

    &.is-wrap {
        flex-wrap: wrap;
    }
}

</style>
