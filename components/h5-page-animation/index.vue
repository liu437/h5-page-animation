<script>
// #ifdef H5
var firstShow = true;
// #endif
import './index.css';
export default {
    // #ifdef H5
    onLaunch: function() {
        if (firstShow) {
            const page1_class = document.querySelector('uni-page').classList;
            page1_class.add('block');
            document.write('<uni-page2 id="page2"></uni-page2>');
        }
        firstShow = false;

        var _this = this;
        this.$router.beforeEach((to, from, next) => {
            // tabBar切换无动画
            if (to.type == 'switchTab') {
                next && next();
                setTimeout(() => {
                    const page1_class = document.querySelector('uni-page').classList;
                    page1_class.add('block');
                }, 10);
                return;
            }

            // 页面回退动画
            if (!to.type || to.type == 'navigateBack') {
                this.hide(next);
                return;
            }

            // 页面跳转动画
            this.show(next);
        });
    },
    methods: {
        hide(next) {
            // 滚动条高度
            var sh = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop || 0;

            // 创建虚拟页
            var page2 = document.getElementById('page2');
            page2.innerHTML = document.querySelector('uni-page').innerHTML;
            // 调整虚拟页样式
            const page2_class = page2.classList;
            // 保持滚动高度
            var sh = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop || 0;
            page2.querySelector('uni-page-wrapper').style.cssText = 'margin-top:-' + sh + 'px';
            page2_class.add('z-index-High');
            page2_class.add('block');
            // 调整真实页样式
            next && next();
            setTimeout(() => {
                // 动画起点
                const page1_class = document.querySelector('uni-page').classList;
                page1_class.add('animation-enter');
                page1_class.add('block');
                // 动画开始
                setTimeout(() => {
                    page1_class.add('animation', 'animation-after');
                    page2_class.add('animation', 'animation-before');
                    // 动画结束
                    setTimeout(() => {
                        page1_class.remove('animation', 'animation-after', 'animation-enter');
                        page2_class.remove('block', 'z-index-High', 'animation-before');
                        page2.innerHTML = '';
                    }, 310);
                }, 100);
            }, 10);
        },
        show(next) {
            // 滚动条高度

            // 创建虚拟页
            var page2 = document.getElementById('page2');
            page2.innerHTML = document.querySelector('uni-page').innerHTML;
            // 调整虚拟页样式
            const page2_class = page2.classList;
            // 保持滚动高度
            var sh = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop || 0;
            page2.querySelector('uni-page-wrapper').style.cssText = 'margin-top:-' + sh + 'px';
            // 显示
            page2_class.add('block');
            // 调整真实页样式
            next && next();
            setTimeout(() => {
                // 动画起点
                const page1_class = document.querySelector('uni-page').classList;
                page1_class.add('animation-before');
                setTimeout(() => {
                    page2_class.add('z-index-low');
                    page1_class.add('block');
                    // 动画开始
                    setTimeout(() => {
                        page1_class.add('animation', 'animation-after');
                        page2_class.add('animation', 'animation-enter');
                        // 动画结束
                        setTimeout(() => {
                            page1_class.remove('animation', 'animation-before', 'animation-after');
                            page2_class.remove('block', 'z-index-low', 'animation', 'animation-enter');
                            page2.innerHTML = '';
                        }, 310);
                    }, 100);
                }, 100);
            }, 10);
        }
    }
    // #endif
};
</script>
