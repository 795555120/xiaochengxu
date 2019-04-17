<template>
  <div >
    <i-notice-bar icon="systemprompt" loop>
    漫文寨测试版1.0上线了，欢迎大家！
    </i-notice-bar>

    <i-grid>
      <i-grid-item>
        <i-grid-icon>
            <image src="../../static/images/shu.png" />
        </i-grid-icon>
        <i-grid-label>漫画</i-grid-label>
      </i-grid-item>
      <i-grid-item>
        <i-grid-icon>
            <image src="../../static/images/shu2.png" />
        </i-grid-icon>
        <i-grid-label>网文</i-grid-label>
      </i-grid-item>
      <i-grid-item>
        <i-grid-icon>
            <image src="../../static/images/shu3.png" />
        </i-grid-icon>
        <i-grid-label>同人</i-grid-label>
      </i-grid-item>
    </i-grid>
    <i-panel title="热榜">
      <view style="padding: 0px;"> 
        <i-card title="鹿瑶知马力"  thumb ="http://imgsrc.baidu.com/forum/pic/item/0135c3ed8a136327d67207349f8fa0ec09fac702.jpg">
            <view slot="content">不知道为什么</view>
            <view slot="footer">柠檬它围绕着我</view>
        </i-card>   
      </view>
    </i-panel>
  </div>
</template>

<script>
import { formatTime } from '@/utils/index'
import card from '@/components/card'

export default {
  components: {
    card
  },

  data () {
    return {
      logs: [],
      imgUrls: [
        'http://mss.sankuai.com/v1/mss_51a7233366a4427fa6132a6ce72dbe54/newsPicture/05558951-de60-49fb-b674-dd906c8897a6',
        'http://mss.sankuai.com/v1/mss_51a7233366a4427fa6132a6ce72dbe54/coursePicture/0fbcfdf7-0040-4692-8f84-78bb21f3395d',
        'http://mss.sankuai.com/v1/mss_51a7233366a4427fa6132a6ce72dbe54/management-school-picture/7683b32e-4e44-4b2f-9c03-c21f34320870'
      ]
    }
  },

  created () {
    let logs
    if (mpvuePlatform === 'my') {
      logs = mpvue.getStorageSync({key: 'logs'}).data || []
    } else {
      logs = mpvue.getStorageSync('logs') || []
    }
    this.logs = logs.map(log => formatTime(new Date(log)))
  }
}
</script>

<style>
.log-list {
  display: flex;
  flex-direction: column;
  padding: 40rpx;
}

.log-item {
  margin: 10rpx;
}
</style>

