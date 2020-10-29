<template>
    <div class="root">
        <h1>技能</h1>
        <div class="skills">
            <div class="word">Nuxt：基于Vue.js 的轻量级应用框架，可创建服务端渲染(SSR)应用，也可建立静态站点应用</div>
            <div class="word">Layui：基于jq的前端 UI 框架</div>
            <div class="word">Antd组件库：蚂蚁集团推出的基于ant design设计语言的组件库</div>
            <div class="word">Stylus：富有表现力的、动态的、健壮的CSS预处理器</div>
            <div class="word">其他：HTML、JS、CSS、Git、Vue、jQuery、WebStorm等</div>
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
    .skills{
        color white
        display flex
        flex-direction column
        flex-wrap wrap
        justify-content center
        padding 0 1rem
        margin-top 10px
    }
    .word
        padding 5px 10px
        margin 5px
        line-height 1.5rem

</style>
