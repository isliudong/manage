<template>
  <div class="login_container">
    <div class="login_box">
      <div class="avatar_box">
        <img src="../assets/img/6956b4a5c128a199cfd53c5315ddb7b3.gif">
      </div>
      <el-form :model="loginForm" :rules="loginRules" ref="loginForm" label-width="0px" class="login-form">
        <el-form-item  prop="username">
          <el-input v-model="loginForm.username" prefix-icon="el-icon-user-solid"></el-input>
        </el-form-item>
        <el-form-item  prop="password">
          <el-input v-model="loginForm.password" prefix-icon="el-icon-lock"></el-input>
        </el-form-item>
        <el-form-item  prop="verifyCode">
          <div class="verifyCode_box">
            <el-input v-model="loginForm.verifyCode" placeholder="请输入验证码" prefix-icon="el-icon-mobile" class="verify_code"></el-input>
            <img src="../assets/img/msFzVK.gif" class="verify_img">
          </div>
        </el-form-item>
        <el-form-item class="login-btn">
          <el-button type="primary" @click="submitForm('loginForm')">立即创建</el-button>
          <el-button @click="resetForm('loginForm')">重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Login',
    data() {
      return {
        loginForm: {
          username: '',
          password: '',
          verifyCode: '',
        },
        loginRules: {
          username: [
            { required: true, message: '请输入用户名', trigger: 'blur' },
            { min: 1, max: 16, message: '长度在 1 到 16 个字符', trigger: 'blur' }
          ],
          password: [
            { required: true, message: '请输入登录密码', trigger: 'blur' },
            { min: 3, max: 16, message: '长度在 3 到 16 个字符', trigger: 'blur' }
          ],
          verifyCode: [
            { required: true, message: '请输入验证码', trigger: 'blur' }
          ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            this.$router.push("/main")
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>

<style lang="less" scoped>
  .login_container {
    height: 100%;
    background-color: aquamarine;
  }

  .login_box{
    width: 450px;
    height: 380px;
    background-color: aliceblue;
    border-radius: 3px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    .avatar_box{
      width: 130px;
      height: 130px;
      border: 1px solid #eeeeee;
      border-radius: 50%;
      padding: 10px;
      box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
      margin: -65px auto;
      background-color: #ffffff;
      img{
        width: 100%;
        height: 100%;
        border-radius: 50%;
        background-color: #eeeeee;
      }
    }
  }

  .login-form{
    position: absolute;
    width: 100%;
    bottom: 0;
    padding: 0 40px;
    box-sizing: border-box;
    .login-btn{
      display: flex;
      justify-content: flex-end;
    }
    .verifyCode_box{
      display: flex;
      .verify_code{
        width: 70%;
        justify-content: left;
      }
    }
    .verify_img{
      width: 30%;
      height: 45px;
      justify-content: flex-end;
    }
  }

</style>
