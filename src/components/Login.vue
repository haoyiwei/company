<template>
  <div id="login-container">
    <!-- <img src="../assets/img/A.svg" alt=""> -->
    <div id="login-box">
      <div id="login-logo">
        <img src="../assets/img/c.jpg" alt>
      </div>
      <el-form :model="loginForm" ref="refform" label-width="100px">
        <el-form-item label="用户名" prop="username">
          <el-input type="text" v-model="loginForm.username" auto-complete="off"></el-input>
        </el-form-item>
        <el-form-item label="密码" prop="password">
          <el-input type="password" v-model="loginForm.password" auto-complete="off"></el-input>
        </el-form-item>
        <el-form-item>
          <el-col :push="12">
            <el-button type="primary" @click="login">登录</el-button>
            <el-button type="info" @click="reset">重置</el-button>
          </el-col>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    login() {
      this.$router.push('/home')
    },
    reset() {
      this.$refs.refform.resetFields()
    }
  },
  data() {
    return {
      loginForm: {
        username: 'admin',
        password: '1111'
      }
    }
  }
}
</script>

<style lang="less" scoped>
#login-container {
  height: 100%;
  width: 100%;
  background: url('../assets/img/q.jpg') no-repeat;
  background-size: 100%, 100%;
  overflow: hidden;
  #login-box {
    width: 450px;
    height: 350px;
    border-radius: 5px;
    box-shadow: 0, 0, 5px;
    background-color: #0b548a;
    position: absolute;
    left: 75%;
    top: 40%;
    transform: translate(-50%, -50%);
    opacity: 0.8;
    #login-logo {
      border-radius: 51%;
      width: 150px;
      height: 150px;
      position: absolute;
      left: 50%;

      transform: translate(-50%, -50%);
      background: #ccc;
      img {
        border-radius: 51%;
        width: 100%;
        height: 100%;
      }
    }
    .el-form {
      position: absolute;
      bottom: 0;
      box-sizing: border-box;
      width: 100%;
      padding: 0 20px 0 0;
      color: #fff;
      .el-form-item {
        color: #fff;
      }
    }
  }
}
</style>
