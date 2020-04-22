<template>
    <el-container class="container">
        <el-header height="100px" class="header">
            <h1>WebSocket聊天室</h1>
            <el-button type="primary">退出登录</el-button>
        </el-header>
        <el-container>
            <el-aside width="200px" class="aside">
                <el-menu
                  :default-active="activeIndex"
                  class="el-menu-vertical-demo"
                  @select="handleSelect"
                  background-color="#545c64"
                  text-color="#fff"
                  active-text-color="#ffd04b"
                  router>
                    <el-menu-item :index="''+index" v-for="(item, index) in friend" :key="index">
                        <i class="el-icon-user-solid"></i>
                        <span slot="title">{{item}}</span>
                    </el-menu-item>
                </el-menu>
            </el-aside>
            <el-main class="main">
                <router-view></router-view>
            </el-main>
        </el-container>
    </el-container>
</template>

<script>
    export default {
        data(){
            return {
                friend: ['张三', '李四', '王五', '赵六'],
                activeIndex: ''
            }
        },
        methods: {
            handleSelect() {
            }
        },
        created() {}
    }
</script>

<style lang="less" scoped>
    .container{
        height: 100%;
    }
    .main{
        background-color: #e4fffb;
    }
    .aside{
        background-color: #c4e2ff;
    }
    .header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #c4e2ff;
    }
    .el-menu-item{
        position: relative;
        width: 100%;
    }
</style>
