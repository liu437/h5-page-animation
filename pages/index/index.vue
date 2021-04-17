<template>
    <view class="content">
        <view class="test-btn"><button type="primary" @tap.stop="toTestPage">navigateTo 跳转</button></view>
        <view class="test-title">望庐山瀑布</view>
        <view class="test-content">
            日照香炉生紫烟，遥看瀑布挂前川。
            <br />
            飞流直下三千尺，疑是银河落九天。
        </view>
        <view class="test-title">早发白帝城</view>
        <view class="test-content">
            朝辞白帝彩云间，千里江陵一日还。
            <br />
            两岸猿声啼不住，轻舟已过万重山。
        </view>
        <view class="test-title">赠汪伦</view>
        <view class="test-content">
            李白乘舟将欲行，忽闻岸上踏歌声。
            <br />
            桃花潭水深千尺，不及汪伦送我情。
        </view>
        <view class="test-title">望天门山</view>
        <view class="test-content">
            天门中断楚江开，碧水东流至此回。
            <br />
            两岸青山相对出，孤帆一片日边来。
        </view>
        <view class="test-btn"><button type="primary" @tap.stop="toTestPage">navigateTo 跳转</button></view>
    </view>
</template>
<script>
export default {
    data() {
        return {
            title: 'Hello'
        };
    },
    onLoad() {},
    methods: {
        toTestPage() {
            uni.navigateTo({
                url: '/pages/test/test'
            });
        }
    }
};
</script>

<style>
.content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 30rpx;
}

.test-btn {
    margin-top: 60rpx;
}

.test-title {
    margin-top: 60rpx;
    font-size: 40rpx;
    font-weight: bold;
}

.test-content {
    width: 670rpx;
    padding: 20rpx 40rpx;
    line-height: 80rpx;
    background-color: rgba(0, 122, 255, 0.15);
    margin-top: 30rpx;
    font-size: 32rpx;
    box-sizing: border-box;
    text-align: center;
    color: #666666;
    border-radius: 10rpx;
}
</style>
