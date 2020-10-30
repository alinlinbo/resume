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
          <img src="../assets/head.jpg">
        </div>
      </div>
      <div class="title">
        <font-awesome-icon icon="th-large"/>&nbsp;个人项目
      </div>
      <div class="projectName">博客后台管理系统</div>
      <div>使用Layui开发的博客后台管理系统，实现了文章管理，用户管理，评论管理等模块前端页面的编写与接口的对接，在项目中对ajax请求进行封装，为接口调用添加了拦截器和loading动画，有效减少代码量并提高开发效率
      </div>
      <div class="projectName">蘑菇街项目</div>
      <div>使用vue开发的移动端商城项目，实现了首页，详情页数据的展示，
        以及商品添加购物车功能，针对业务场景封装了滚动容器、
        底部及顶部导航栏、轮播图等公用组件，提高代码复用
      </div>
      <div class="title">
        <font-awesome-icon icon="briefcase"/>&nbsp;工作经历
      </div>
      <div class="projectName">中国人寿珠海分公司</div>
      <div class="workTitle">
        <strong>工作内容</strong>
        <div class="workTime">2019-08~2020-06</div>
      </div>
      <div class="workContent">
        1. 使用vb脚本处理excel表格
        <br>
        2. ps制图以及一些基本的数据录入
      </div>

      <div class="projectName">珠海客官点评科技有限公司</div>
      <div class="workTitle">
        <strong>工作内容</strong>
        <div class="workTime">2018-03~2019-01</div>
      </div>
      <div class="workContent">
        1. 使用PS和AI制作海报和插图以及一些图标。
        <br>2. 通过一些线上渠道拓展公司业务
      </div>
      <div class="title">
        <font-awesome-icon icon="th-large"/>&nbsp;技能&自我评价
      </div>
      <div class="skills">
        <ul>
          <li>热爱编程，具有一定的自学能力，熟悉<span>HTML5</span>新特性以及其代码编写，能够根据交互原型和UI设计图还原出页面</li>
          <li>熟悉Flex布局、媒体查询、transition动画等<span>CSS3</span>新特性，对<span>Stylus</span>等css预处理有一定了解</li>
          <li>熟悉Promise、Class等<span>ES6+</span>新的语言特性，对事件传递、原型链、继承、作用域等问题有一定了解，了解http协议，熟练使用<span>Ajax</span>做前后台数据交互</li>
          <li>熟练使用<span>Vue、jq</span>等框架进行项目开发，熟悉<span>Nuxt.js</span>框架（基于Vue的支持SSR后端渲染的轻量级框架）、<span>LayUI</span>框架（基于jq的UI框架）、<span>ant design</span>组件库</li>
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
        window.open('http://pn5jqyvqw.bkt.clouddn.com/%E9%99%88%E6%A0%A1%E5%9F%B9-%E7%AE%80%E5%8E%86.pdf')
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
            val: '1996-02',
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
            val: 'github.com/alinlinbo',
            icon: 'code'
          }
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
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

  @media screen and (min-width: 769px)

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
    display none
    position fixed
    right 1rem
    bottom 0
    flex-direction column
    align-items center

    img
      width 5rem
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

  .word
    margin: 4px
    padding: 6px
    border-radius: 16px
    border: white 1px solid
    font-size: 16px


  .container
    display: flex


  .left
    background-color: #29B6F6
    display: flex
    flex-direction: column
    color: white


  .avatar
    margin: 0px auto
    margin-right: 22px
    width: 120px
    height: 120px
    border: 1px solid whitesmoke
    background-color: white

    img
      width 100%
      height 100%


  .personInfo
    margin-left: 22px
    font-size: 15px


  .personInfo
    .row
      margin-top: 10px

      svg
        width 20px
        text-align center

  .aboutMe
    display flex

</style>
