<template>
    <view class="content">
        <view class="test-btn"><button type="warn" @tap.stop="toIndexPage">navigateTo 返回</button></view>
        <view class="test-title">长恨歌</view>
        <view class="test-content">
            汉皇重色思倾国，御宇多年求不得。 杨家有女初长成，养在深闺人未识。 天生丽质难自弃，一朝选在君王侧。 回眸一笑百媚生，六宫粉黛无颜色。 春寒赐浴华清池，温泉水滑洗凝脂。
            侍儿扶起娇无力，始是新承恩泽时。 云鬓花颜金步摇，芙蓉帐暖度春宵。 春宵苦短日高起，从此君王不早朝。 承欢侍宴无闲暇，春从春游夜专夜。 后宫佳丽三千人，三千宠爱在一身。
            金屋妆成娇侍夜，玉楼宴罢醉和春。 姊妹弟兄皆列土，可怜光彩生门户。 遂令天下父母心，不重生男重生女。 骊宫高处入青云，仙乐风飘处处闻。 缓歌慢舞凝丝竹，尽日君王看不足。
            渔阳鼙鼓动地来，惊破霓裳羽衣曲。 九重城阙烟尘生，千乘万骑西南行。 翠华摇摇行复止，西出都门百余里。 六军不发无奈何，宛转蛾眉马前死。 花钿委地无人收，翠翘金雀玉搔头。
        </view>
        <view class="test-btn"><button type="warn" @tap.stop="toIndexPage">navigateTo 返回</button></view>
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
        toIndexPage() {
            uni.navigateBack({
                delta: 1
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
    background-color: rgba(230, 67, 64, 0.15);
    margin-top: 30rpx;
    font-size: 32rpx;
    box-sizing: border-box;
    text-align: center;
    color: #666666;
    border-radius: 10rpx;
}
</style>
