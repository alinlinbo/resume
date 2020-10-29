<template>
    <div class="root">
        <h1>技能</h1>
        <!--<div class="skills" v-for="(s,index) in skills" :key="index">
            <div class="word" v-for="(item,index) in s" :key="index">
                {{item}}
            </div>
        </div>-->
        <div class="skills">
            <div>nuxt：一个基于 Vue.js , 主要关注应用的 UI 渲染的通用应用框架</div>
            <div>layui：一个基于jq的前端 UI 框架</div>
            <div>其他：HTML、JS、CSS、Git、Vue、jq....</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Skill",
        data() {
            return {
            }
        }
    }
</script>

<style scoped lang="stylus">
    @media only screen and (max-width: 768px)
        .skills
            font-size 1rem
            line-height @font-size
    @media screen and (min-width: 769px)
        .skills
            font-size 1.5rem
            line-height @font-size
    .root
        background-color #22c3aa
        display flex
        flex-direction column
        justify-content center
        align-items center

/*    .skills
        display flex
        flex-wrap wrap
        justify-content center
        padding 0 1rem
        margin-top 10px
        .word
            background-color #00796b
            color #f3f3f3
            border-radius 5px
            padding 5px 10px
            margin 5px*/
    .skills{
        color white
    }

</style>
