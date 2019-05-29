<template>
  <div >
    <i-notice-bar icon="systemprompt" loop>
    漫文寨测试版1.0上线了，谢谢大家的支持！
    </i-notice-bar>

    <i-grid i-class="no-border">
      <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
      </i-grid-item>
    </i-grid>

    <i-panel :title="title_name">
      <view style="padding: 0px;"> 
        <i-card v-for="item in top" :key="item" :title="item.name" :thumb ="item.image">
            <view slot="content">{{item.author}}</view>
            <view slot="footer">{{item.remark}}</view>
        </i-card>   
      </view>
    </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title_name:"热榜",
      grids:[
        {title:"漫画",image:"../../static/images/shu.png"},
        {title:"网文",image:"../../static/images/shu2.png"},
        {title:"同人",image:"../../static/images/shu3.png"}
      ],
      top:[
        {name:"鹿瑶知马力",author:"不知道为什么",image:"http://imgsrc.baidu.com/forum/pic/item/0135c3ed8a136327d67207349f8fa0ec09fac702.jpg",remark:"柠檬它围绕着我"},
        {name:"青春奇妙物语",author:"两色风景",image:"https://gss2.bdstatic.com/-fo3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=2fd976ab247f9e2f6438155a7e598241/7aec54e736d12f2e376a6a2d4cc2d56285356814.jpg",remark:"有趣的校园幻想小说"},
        {name:"龙族V",author:"江南",image:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557900813064&di=e28a2e48e9b0d1c0fe7ddc3810a937d6&imgtype=0&src=http%3A%2F%2Fi-1.binzz.com%2F2018%2F6%2F22%2Fdaaa570f-40ad-4936-9eec-cb178dc4ab26.jpg%3Fwidth%3D768%26height%3D1024",remark:"挖坑青年江南的中年填坑之路"},
        {name:"将夜",author:"猫腻",image:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557900931053&di=09181105ff0fd8d82dc78ed18e348101&imgtype=0&src=http%3A%2F%2Fn.sinaimg.cn%2Fent%2Ftransform%2F20161117%2FHfQO-fxxwrwk1331170.jpg",remark:"网上各种梗大家应该都看过"}
        ]
    }
  },

  methods: {
    goList (url) {
      mpvue.navigateTo({ url })
    },
    goType(type){
      console.log(type)
      let url = '../logs/main?type=' + type.title
      mpvue.navigateTo({ url })
    }
  },

  created () {
    
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

