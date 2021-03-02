<template>
    <div class="root">
            <img id="avatar" src="../assets/head.jpg"/>
        <h1>陈燕灵</h1>
        <div class="subTitle">前端开发</div>
    </div>
</template>

<script>
    export default {
        name: "AboutMe"
    }
</script>

<style scoped lang="stylus">
    .root
        display flex
        flex-direction column
        justify-content center
        align-items center
        background-color #22c3aa

    #avatar
        width 200px
        height @width
        border 10px solid #aee2d9
        border-radius 50%
    .subTitle
        color #aee2d9
        font-size 1.4rem
        padding 0 2rem
        text-align center

</style>
