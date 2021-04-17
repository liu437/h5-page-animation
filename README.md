# h5-page-animation
uniapp插件。解决uniapp框架下H5端页面切换无过渡动画的问题，并完美模拟APP双层页面动画。

### 一、目录结构

```
project                 项目目录
├─components            组件目录
│  └─h5-page-animation  本插件目录
│  │  ├─index.vue       本插件主文件
│  │  └─index.css       本插件主样式文件
│  ...
```

### 二、安装说明

1、复制 h5-page-animation 文件夹，粘贴到 uniapp 项目中的 components 组件目录内。

2、在 App.vue 文件内，使用 mixins 引入 h5-page-animation 插件。

```vue
<script>
// #ifdef H5
import h5PageAnimation from './components/h5-page-animation/';
// #endif
export default {
    // #ifdef H5
    mixins: [h5PageAnimation],
    // #endif
    onLaunch: function() {
        console.log('App Launch');
    },
    onShow: function() {
        console.log('App Show');
    },
    onHide: function() {
        console.log('App Hide');
    }
};
</script>
```

### 三、适用说明

本插件仅支持uniapp框架下H5端