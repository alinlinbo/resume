<template>
    <div class="root">
        <h1>个人项目</h1>
        <div class="carousel">
            <el-carousel arrow="always" trigger="click" :autoplay="false" height="360px">
                <el-carousel-item class="item" v-for="(item,index) in projects" :key="index">
                    <a :href="item.url" target="_blank" class="projectTitle">{{ item.title }}</a>
                    <div class="content">{{item.content}}</div>
                </el-carousel-item>
            </el-carousel>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Project",
        data() {
            return {
                projects: [
                    {
                        title: '博客后台管理系统',
                        url: 'https://github.com/alinlinbo/blog-admin-web',
                        icon: '',
                        content: '使用Layui开发的博客后台管理系统，实现了文章管理，用户管理，' +
                            '评论管理等模块前端页面的编写与接口的对接，在项目中对ajax请求进行封装，' +
                            '为接口调用添加了拦截器和loading动画，有效减少代码量并提高开发效率'
                    },
                    {
                        title: '个人线上简历',
                        url: 'https://github.com/alinlinbo/resume',
                        icon: '',
                        content: '使用vue开发的个人线上简历，利用媒体查询和Rem特性同时适配了PC端和移动端，且实现了用户调用浏览器打印页面时自动隐藏交互按钮并显示网站二维码的功能'
                    },{
                        title: '蘑菇街项目',
                        url: 'https://github.com/alinlinbo/supermall',
                        icon: '',
                        content: '使用vue开发的移动端商城项目，实现了首页，详情页数据的展示，以及商品添加购物车功能，针对业务场景封装了滚动容器、底部及顶部导航栏、轮播图等公用组件，提高代码复用'
                    }

                ]
            }
        }
    }
</script>

<style scoped lang="stylus">
    @media screen and (min-width: 769px)
        .content
            width 60%
            font-size 1.5rem

    .root
        display flex
        flex-direction column
        align-items center
        justify-content center
        background-color #00BCD4
        overflow auto

    .carousel
        width 100%
        margin-top 1rem

        .item
            display flex
            flex-direction column
            align-items center

            .content
                text-align center
                margin 1rem 3.5rem
                font-size 1.2rem
                color #f5f5f5

    .projectTitle
        transition all 300ms
        font-size 2.5rem
        color darkslategrey
        border-bottom 2px darkslategray solid
    .projectTitle:hover
        color #9f3
        border-bottom-color: #9f3
</style>
