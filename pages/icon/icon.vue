<template>
    <view class="demo-icon">
        <view v-for="item in list" :key="item.label">
            <SunnyIcon :name="item.value" ></SunnyIcon>
            <text>{{item.label}}</text>
        </view>
    </view>
</template>

<script>
    import SunnyIcon from '../../components/SunnyIcon/SunnyIcon';
    export default {
        components: {SunnyIcon},
        data() {
            return {
                list: [
                    {
                        label: 'notification',
                        value: 's-icon-notification'
                    },
                    {
                        label: 'notification-fill',
                        value: 's-icon-notification-fill'
                    },
                    {
                        label: 'info',
                        value: 's-icon-info'
                    },
                    {
                        label: 'info-fill',
                        value: 's-icon-info-fill'
                    },
                    {
                        label: 'arrow-top',
                        value: 's-icon-arrow-top'
                    },
                    {
                        label: 'arrow-right',
                        value: 's-icon-arrow-right'
                    },
                    {
                        label: 'arrow-bottom',
                        value: 's-icon-arrow-bottom'
                    },
                    {
                        label: 'arrow-left',
                        value: 's-icon-arrow-left'
                    },
                    {
                        label: 'question',
                        value: 's-icon-question'
                    },
                    {
                        label: 'question-fill',
                        value: 's-icon-question-fill'
                    },
                    {
                        label: 'toast-waiting',
                        value: 's-icon-toast-waiting'
                    },
                    {
                        label: 'toast-warnings',
                        value: 's-icon-toast-warning'
                    },
                    {
                        label: 'toast-success',
                        value: 's-icon-toast-success'
                    },
                    {
                        label: 'toast-error',
                        value: 's-icon-toast-error'
                    },
                    {
                        label: 'avatar',
                        value: 's-icon-avatar'
                    },
                    {
                        label: 'plus',
                        value: 's-icon-plus'
                    },
                    {
                        label: 'minus',
                        value: 's-icon-minus'
                    },
                    {
                        label: 'image',
                        value: 's-icon-image'
                    },
                    {
                        label: 'check',
                        value: 's-icon-check'
                    },
                    {
                        label: 'image',
                        value: 's-icon-image'
                    },
                    {
                        label: 'close',
                        value: 's-icon-close'
                    },
                    {
                        label: 'emoji',
                        value: 's-icon-emoji'
                    },
                    {
                        label: 'favor-fill',
                        value: 's-icon-favor-fill'
                    },
                    {
                        label: 'round-check',
                        value: 's-icon-round-check'
                    },
                    {
                        label: 'round-check-fill',
                        value: 's-icon-round-check-fill'
                    },
                    {
                        label: 'round-close',
                        value: 's-icon-round-close'
                    },
                    {
                        label: 'round-close-fill',
                        value: 's-icon-round-close-fill'
                    },
                    {
                        label: 'search',
                        value: 's-icon-search'
                    }
                ]
            };
        }
    };
</script>

<style lang="scss"> </style>
