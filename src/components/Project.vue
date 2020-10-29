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
                        //url: 'https://www.microsoft.com/zh-cn/p/每日一文-uwp/9nblggh51w0r',
                        icon: '',
                        content: '用layui开发的一个博客后台管理系统，实现了文章管理，用户管理，评论管理等模块前端页面的编写与接口的对接'
                    }, {
                        title: '蘑菇街项目',
                        //url: 'https://www.microsoft.com/zh-cn/p/码农日历/9nblggh526sj',
                        icon: '',
                        content: '使用vue框架的一个项目，实现了首页，详情页数据的展示，以及商品添加购物车功能'
                    }

                ]
            }
        }
    }
</script>

<style scoped lang="stylus">
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
                font-size 1.5rem
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
