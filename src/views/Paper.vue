<template>
  <div class="container">
    <div class="notPrint">
      <div class="floatBtns ">
        <div class="downloadBtn floatButton" @click="downloadResume">
          <font-awesome-icon icon="download"/>
          <div class="text">下载简历</div>
        </div>
      </div>
    </div>
    <div class="notPrint">
      <div class="backBtn" @click="$router.replace('/')" :style="'transform: translateY('+position+'px)'">
        <font-awesome-icon icon="home"/>
      </div>
    </div>
    <div class="right">
      <div class="name">陈燕灵</div>
      <div class="aboutMe">
        <div class="personInfo">
          <div class="row" v-for="(item,index) in personalInfo" :key="index">
            <font-awesome-icon :icon="item.icon"/>
            &nbsp;{{ item.val }}
          </div>
        </div>
        <div class="avatar">
          <img src="../assets/head-paper.jpg">
        </div>
      </div>
      <div class="title">
        <font-awesome-icon icon="th-large"/>&nbsp;项目
      </div>
      <div class="projectName">系统中台</div>
      <div>基于guns框架，使用ant design组件开发的业务中台

      </div>
      <div class="projectName">商城管理后台</div>
      <div>使用avue框架和element-ui开发的商城管理后台，实现了优惠券、文章管理、会员管理等模块部分接口对接与前端小程序页面的编写

      </div>
      <div class="projectName">iSmart Mall小程序</div>
      <div>基于uni-app框架开发的微信小程序商城，项目使用Uvue组件和uni-app自带的组件，完成了购物、详情、提交订单等模块的接口对接及样式修改
      </div>
      <div class="title">
        <font-awesome-icon icon="briefcase"/>&nbsp;工作经历
      </div>
      <div class="work">
        <div>
          <div class="projectName">中国人寿珠海分公司</div>
          <div class="workTitle">
            <strong>资料录入员</strong>
            <div class="workTime">2019-08~2020-06</div>
          </div>
          <div class="workContent">
            1. 使用vb脚本处理excel表格
            <br>
            2. ps制图以及一些基本的数据录入
          </div>
        </div>

        <div class="workItem">
          <div class="projectName">珠海横琴智恒运通网络科技有限公司</div>
          <div class="workTitle">
            <strong>前端开发</strong>
            <div class="workTime">2020-11~2021-02</div>
          </div>
          <div class="workContent">
            1. 使用vue、avue框架还原设计图以及页面交互
          </div>
        </div>
      </div>
      <div class="title">
        <font-awesome-icon icon="th-large"/>&nbsp;技能&自我评价
      </div>
      <div class="skills">
        <ul>
          <li>热爱编程，具有一定的自学能力，熟悉<span>HTML5</span>新特性以及其代码编写，能够根据交互原型和UI设计图还原出页面</li>
          <li>熟悉Flex布局、媒体查询、transition动画等<span>CSS3</span>新特性，对<span>Stylus</span>等css预处理有一定了解</li>
          <li>熟悉Promise、Class等<span>ES6+</span>新的语言特性，对事件传递、原型链、继承、作用域等问题有一定了解，了解http协议，熟练使用<span>Ajax</span>做前后台数据交互</li>
          <li>熟练使用<span>Vue、jq</span>等框架进行项目开发，熟悉<span>avue.js</span>框架（基于现有的element-ui库进行的二次封装）、<span>ant design</span>组件库</li>
          <li>熟练<span>Git</span>、<span>WebStorm</span>、<span>Photoshop</span>等开发工具</li>
        </ul>
      </div>
      <div class="qrCode">
        <img src="../assets/qrCode.png">
        <div>扫码查看线上简历</div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    components: {},
    methods: {
      downloadResume() {
        window.open('https://resource-alinlinbo.obs.cn-south-1.myhuaweicloud.com/%E9%99%88%E7%87%95%E7%81%B5-%E5%89%8D%E7%AB%AF%E6%B1%82%E8%81%8C-%E7%AE%80%E5%8E%86.pdf')
      }
    },
    mounted() {
      let that = this
      document.body.onmousewheel = function (event) {
        let e = event || window.event;
        if (e.wheelDelta) {
          if (e.wheelDelta > 0) {
            that.position = 0
          }
          if (e.wheelDelta < 0) {
            that.position = -60
          }
        } else if (e.detail) {
          if (e.detail > 0) {
            that.position = 0
          }
          if (e.detail < 0) {
            that.position = -60
          }
        }
      };
    },
    data() {
      return {
        position: 0,
        personalInfo: [
          {
            val: '求职意向：前端开发',
            icon: 'user'
          },
          {
            val: '专业：软件技术',
            icon: 'calendar-alt'
          }, {
            val: '1年开发经验',
            icon: 'briefcase'
          }, {
            val: '15919213326',
            icon: 'phone'
          }, {
            val: '1144381579@qq.com',
            icon: 'envelope'
          }, {
            val: '薪资要求：5k',
            icon: 'yen-sign'
          },  {
            val: 'github.com/alinlinbo',
            icon: 'code'
          }
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .personInfo
    font-size: 1rem
  .avatar
    margin: 0px auto
    margin-right: 22px
    width: 120px
    background-color: white
    img
      width 100%

  @media print
    .notPrint
      display none
    .container
      .qrCode
        display flex

  @media only screen and (max-width: 768px)
    .container
      flex-direction column
      width 100%

    .right
      width 100%

    .left
      width 100%

    .notPrint
      display none

  @media  screen and (max-width: 360px)
    .avatar
      margin: 0px auto
      margin-right: 0px
      width: 80px
      background-color: white

    img
      width 100%

    .personInfo
      font-size: 1rem

  .workTitle
    display flex
    flex-wrap wrap
    strong
      margin-right: 1rem;
    .workTime
      margin-top 0.3rem

  .work
    display flex
    flex-wrap wrap

    div
      min-width 280px
      flex 1
  @media screen and (min-width: 768px)

    .container
      flex-direction row
      width: 21cm
      height: 297mm
      margin: 10px auto
      box-shadow: 0 2px 2px 0 rgba(0, 0, 0, .14), 0 3px 1px -2px rgba(0, 0, 0, .2), 0 1px 5px 0 rgba(0, 0, 0, .12)
      overflow: hidden
      border-radius: 4px

    .left
      width 240px
      padding 6px
      box-sizing border-box

  .skills
    ul
      margin-left 1rem
      margin-top 0.5rem
      li
        list-style disc
    span
      background #29B6F6
      border-radius 4px
  .backBtn
    position fixed
    transition: transform 300ms
    top 5px
    left @top
    width 36px
    height @width
    background-color #7C4DFF
    opacity 0.5
    cursor pointer
    display flex
    align-items center
    justify-content center
    border-radius 50%

    svg
      color white

  .floatBtns
    position fixed
    display flex
    flex-direction column
    bottom 48px
    right 48px
    color white
    width 120px
    text-align center
    align-items center

    .printBtn
      background-color #FF4081

    .downloadBtn
      background-color #7C4DFF

    .floatButton
      cursor pointer
      margin-top 16px
      transition: all 300ms
      width 64px
      height @width
      border-radius @width
      box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.14), 0 5px 7px -2px rgba(0, 0, 0, 0.2), 0 4px 5px 0 rgba(0, 0, 0, 0.12)
      .text
        font-size 18px
        display none
        margin-top 18px
        white-space nowrap
      svg
        font-size 32px
        margin-top 16px
    .floatButton:hover
      width 120px
      opacity .8
      .text
        display block
      svg
        display none


  .qrCode
    font-size 0.8rem
    width 10rem
    display none
    position fixed
    right 1rem
    bottom 0
    flex-direction column
    align-items center

    img
      margin 0 auto
      width 50%
      height auto

  .workTitle
    display flex
    justify-content space-between

  .workContent
    margin-top 5px
    font-size 14px

  .name
    font-size 32px
    margin-top 15px

  .projectName
    font-size 18px
    font-weight bold
    margin 8px 0

  .right
    flex: 1
    padding: 0 20px
    box-sizing border-box
    display flex
    flex-direction column
    align-items stretch

  .title
    color: #29B6F6
    font-size: 22px
    border-bottom: #29B6F6 1px solid
    margin-top 24px
    margin-bottom 5px

  .skillKeyWord
    display: flex
    flex-wrap: wrap
    justify-content: space-evenly
    padding 5px 0

  .container
    display: flex


  .left
    background-color: #29B6F6
    display: flex
    flex-direction: column
    color: white

  .personInfo
    .row
      margin-top: 10px

      svg
        width 20px
        text-align center

  .aboutMe
    display flex

</style>
