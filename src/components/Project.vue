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
                        icon: '',
                        content: '使用Layui开发的博客后台管理系统，实现了文章管理，用户管理，评论管理等模块前端页面的编写与接口的对接'
                    }, {
                        title: '蘑菇街项目',
                        icon: '',
                        content: '使用vue开发的移动端商城项目，实现了首页，详情页数据的展示，以及商品添加购物车功能'
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
</style>
