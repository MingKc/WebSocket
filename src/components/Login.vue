<template>
    <div class="container">
        <div class="box">
            <el-form ref="loginFormRef" :model="loginForm" class="login" :rules="loginFormRules">
                <el-form-item prop="username">
                    <el-input v-model="loginForm.username" prefix-icon="el-icon-user-solid"></el-input>
                </el-form-item>
                <el-form-item prop="password">
                    <el-input v-model="loginForm.password" prefix-icon="el-icon-s-cooperation" type="password"></el-input>
                </el-form-item>
                <el-form-item class="btns">
                    <el-button type="primary" size="mini" @click="resetForm">重置</el-button>
                    <el-button type="success" size="mini" @click="login">登录</el-button>
                </el-form-item>
            </el-form>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                // 表单数据对象
                loginForm: {
                    username: '',
                    password: ''
                },
                // 表单数据校验对象
                loginFormRules: {
                    username: [
                        { required: true, message: '请输入用户名', trigger: 'blur' }
                    ],
                    password: [
                        { required: true, message: '请输入密码', trigger: 'blur' }
                    ]
                }
            }
        },
        methods: {
            // 重置表单
            resetForm() {
                this.$refs.loginFormRef.resetFields();
            },
            // 登录
            login() {
                this.$refs.loginFormRef.validate(validate => {
                    if (!validate) {
                        return this.$message.error('登录失败！');
                    }
                })
            }
        }
    }
</script>

<style lang="less" scoped>
    .container{
        height:100%;
        background-color:#242662;
        display: flex;
        justify-content: center;
        align-items:center ;
    }
    .box{
        width: 450px;
        height: 300px;
        border-radius: 15px;
        background-color: #fff;
    }
    .login{
        position: relative;
        margin-top: 85px;
        width: 100%;
        box-sizing: border-box;
        padding: 0 20px;
    }
    .btns{
        margin-top: 50px;
        display: flex;
        justify-content:flex-end;
    }
</style>
