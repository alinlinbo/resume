<template>
    <div class="root">
        <h1>工作经历</h1>
        <el-timeline class="timeline">
            <el-timeline-item placement="top" timestamp="2019-01" size="large">
              <div class="company">中国人寿珠海分公司</div>
              <div class="content">使用vb脚本处理excel表格,ps制图以及一些基本的数据录入.
              </div>
            </el-timeline-item>
            <el-timeline-item placement="top" timestamp="2020-11" size="large">
              <div class="company">珠海横琴智恒运通网络科技有限公司</div>
              <div class="content">使用vue、avue框架还原设计图以及页面交互
              </div>
            </el-timeline-item>
            <el-timeline-item timestamp="2021-02" size="large">

            </el-timeline-item>
        </el-timeline>
    </div>
</template>

<script>
    export default {
        name: "Work"
    }
</script>

<style lang="stylus">
    .timeline
        .el-timeline-item__timestamp
            font-size 1.5rem
            color white
</style>

<style scoped lang="stylus">
    @media only screen and (max-width: 768px)
        .timeline
            .company
                font-size 1.2rem

            .content
                font-size 1rem

    @media screen and (min-width: 769px)
        .timeline
            .company
                font-size 1.8rem

            .content
                font-size 1.5rem

    .root
        background-color #009688
        display flex
        flex-direction column
        justify-content center
        align-items center

    .timeline
        padding 0 2rem

        .company
            color white
            margin 5px 0

        .content
            color #B5EDF4
</style>
