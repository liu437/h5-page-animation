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

<style>
/*每个页面公共css */
</style>
