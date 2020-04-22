<template>
    <el-container class="container">
        <el-header></el-header>
        <el-main>Main</el-main>
        <el-footer>
            <el-input
            type="textarea"
            :rows="2"
            placeholder="请输入内容"
            v-model="textarea">
        </el-input>
    </el-footer>
</el-container>
</template>

<script>
    export default {
        data() {
            return {
                textarea: ''
            }
        },
        methods: {},
        created() {}
    }
</script>

<style lang="less" scoped>
    .container{
        height: 100%;
    }
</style>
