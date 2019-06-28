<template>
  <div >
    <i-notice-bar icon="systemprompt" loop>
    漫文寨测试版1.0上线了，谢谢大家的支持！
    </i-notice-bar>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:200px"
    >
    <block v-for="item in imgUrls" :key="item">
      <swiper-item>
        <image :src="item" style="width:100%;"/>
      </swiper-item>
    </block>
  </swiper>
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
        <i-card @click="goList(item.url)" v-for="item in top" :key="item" :title="item.name" :thumb ="item.image">
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
      imgUrls: [
        'https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=1475311644,2439664071&fm=179&app=42&f=JPEG?w=328&h=164.jpg',
        'https://ss3.baidu.com/-rVXeDTa2gU2pMbgoY3K/it/u=645174013,2425845957&fm=202&mola=new&crop=v1.jpg',
        'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=914098589,2376292293&fm=58.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,

      title_name:"热榜",
      grids:[
        {title:"漫画",image:"../../static/images/shu.png"},
        {title:"网络小说",image:"../../static/images/shu2.png"},
        {title:"动漫",image:"../../static/images/shu3.png"}
      ],
      top:[
        {name:"刺客伍六七",author:"B站",image:"https://i0.hdslb.com/bfs/bangumi/8ff39c776f473d8f4fe77910cec59e87ebd1e275.jpg@268w_358h.webp",remark:"高分国漫续作","url":'../logs/main?type=3'},
        {name:"青春奇妙物语",author:"两色风景",image:"https://gss2.bdstatic.com/-fo3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=2fd976ab247f9e2f6438155a7e598241/7aec54e736d12f2e376a6a2d4cc2d56285356814.jpg",remark:"有趣的校园幻想小说","url":'../logs/main?type=2'},
        {name:"一人之下",author:"动漫堂",image:"https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=3869060824,3652350992&fm=58&bpow=449&bpoh=631",remark:"设定很棒的质量漫画","url":'../logs/main?type=3'},
        {name:"将夜",author:"猫腻",image:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1557900931053&di=09181105ff0fd8d82dc78ed18e348101&imgtype=0&src=http%3A%2F%2Fn.sinaimg.cn%2Fent%2Ftransform%2F20161117%2FHfQO-fxxwrwk1331170.jpg",remark:"网上各种梗大家应该都看过","url":'../logs/main?type=2'}
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

