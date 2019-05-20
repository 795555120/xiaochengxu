<template>
  <div >
    <i-notice-bar icon="systemprompt" loop>
    漫文寨测试版1.0上线了，谢谢大家的支持！
    </i-notice-bar>

    <i-grid>
      <i-grid-item i-class="no-border">
        <i-grid-icon i-class="no-border">
            <image src="../../static/images/shu.png" />
        </i-grid-icon>
        <i-grid-label>漫画</i-grid-label>
      </i-grid-item>
      <i-grid-item i-class="no-border">
        <i-grid-icon i-class="no-border">
            <image src="../../static/images/shu2.png" />
        </i-grid-icon>
        <i-grid-label>网文</i-grid-label>
      </i-grid-item>
      <i-grid-item i-class="no-border">
        <i-grid-icon i-class="no-border">
            <image src="../../static/images/shu3.png" />
        </i-grid-icon>
        <i-grid-label>同人</i-grid-label>
      </i-grid-item>
    </i-grid>

    <i-panel :title="title_name">
      <view style="padding: 0px;"> 
        <i-card title="鹿瑶知马力"  thumb ="http://imgsrc.baidu.com/forum/pic/item/0135c3ed8a136327d67207349f8fa0ec09fac702.jpg">
            <view slot="content">不知道为什么</view>
            <view slot="footer">柠檬它围绕着我</view>
        </i-card>   
      </view>
        <view style="padding: 0px;"> 
        <i-card title="青春奇妙物语"  thumb ="https://gss2.bdstatic.com/-fo3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=2fd976ab247f9e2f6438155a7e598241/7aec54e736d12f2e376a6a2d4cc2d56285356814.jpg">
            <view slot="content">两色风景</view>
            <view slot="footer">有趣的校园幻想小说</view>
        </i-card>   
      </view>
        <view style="padding: 0px;"> 
        <i-card title="龙族V"  thumb ="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557900813064&di=e28a2e48e9b0d1c0fe7ddc3810a937d6&imgtype=0&src=http%3A%2F%2Fi-1.binzz.com%2F2018%2F6%2F22%2Fdaaa570f-40ad-4936-9eec-cb178dc4ab26.jpg%3Fwidth%3D768%26height%3D1024">
            <view slot="content">江南</view>
            <view slot="footer">挖坑青年江南的中年填坑之路</view>
        </i-card>   
      </view>
        <view style="padding: 0px;"> 
        <i-card title="将夜"  thumb ="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557900931053&di=09181105ff0fd8d82dc78ed18e348101&imgtype=0&src=http%3A%2F%2Fn.sinaimg.cn%2Fent%2Ftransform%2F20161117%2FHfQO-fxxwrwk1331170.jpg">
            <view slot="content">猫腻</view>
            <view slot="footer">网上各种梗大家应该都看过</view>
        </i-card>   
      </view>
    </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title_name:"热榜"
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

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
div >>> .split {
  margin-bottom: 10pt;
}
</style>

