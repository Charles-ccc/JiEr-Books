<script>
import config from './config'
import {get} from './util'
import qcloud from 'wafer2-client-sdk'
export default {
  created () {
    // 调用API从本地缓存中获取数据
    // const logs = wx.getStorageSync('logs') || []
    // logs.unshift(Date.now())
    // wx.setStorageSync('logs', logs)
    console.log('app created and cache logs by setStorageSync')

    // 设置登录地址
    qcloud.setLoginUrl(config.login);
    qcloud.login({
        success: function (userInfo) {
            console.log('登录成功', userInfo);
        },
        fail: function (err) {
            console.log('登录失败', err);
        }
    });
  },
  
}
</script>

<style>

</style>
