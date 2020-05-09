<template>
    <div class="top-header">

      <div class="right-nav">

        <div class="right-nav-item" v-show="!isLogin" @click="dialogVisible=true">
          登录
        </div>
        <div class="right-nav-item" v-show="isLogin">
          <el-dropdown>
          <span class="drop-item">
            张三 <i class="el-icon-arrow-down el-icon--right"></i>
          </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>修改密码</el-dropdown-item>
              <el-dropdown-item>个人信息</el-dropdown-item>
              <el-dropdown-item>退出登录</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </div>
        <router-link to="/" class="right-nav-item">
          首页
        </router-link>
        <div class="right-nav-item" v-show="isLogin">
          个人中心
        </div>

<!--        <router-link to="/search" class="right-nav-item">-->
<!--          个人中心-->
<!--        </router-link>-->
      </div>

      <el-dialog
        title=""
        :visible.sync="dialogVisible"
        width="400px"
        :append-to-body="true"
        center
        :show-close="false">

        <div class="login-title" style="display: flex;justify-content: center;align-items: center;margin-bottom: 20px;">
          <h2>请登录</h2>
        </div>
        <el-form ref="form" :model="form" label-width="80px">
          <el-form-item label="用户名">
            <el-input v-model="form.name"></el-input>
          </el-form-item>

          <el-form-item label="密码">
            <el-input  v-model="form.password"></el-input>
          </el-form-item>

          <el-form-item >
            <el-button type="primary" @click="login">立即登录</el-button>
          </el-form-item>
        </el-form>
      </el-dialog>
    </div>

</template>

<script>

  export default {
    data() {
      return {
        dialogVisible:false,
        isLogin:true,
        form:{
          name:"",
          password:"",
        },
      }
    },
    mounted:function(){
      let token  = sessionStorage.getItem("token");
      this.isLogin = !!token;
    },
    methods:{
      login:function(){
        sessionStorage.setItem("token","222");
        window.location.reload();
      }
    }
  }
</script>

<style lang="scss" scoped>
  .container{
    display: flex;
    flex-direction: column;
  }
  .top-header{
    position: relative;
    width: 100%;
    z-index: 30;
    height: 40px;
    font-size: 12px;
    color: #b0b0b0;
    background:#003764 ;
    padding: 0;
    display: flex;
    flex-shrink: 0;
    box-sizing: border-box;
  }
  .right-nav{
    position: absolute;
    right: 40px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    top: 10px;
  }
  .drop-item{
    color: #b0b0b0;
    font-size: 13px;
  }
  .right-nav .right-nav-item{
    padding: 0 12px;
    height: 30px;
    font-size: 13px;
    cursor: pointer;
    letter-spacing: 0.3em;
  }
</style>
