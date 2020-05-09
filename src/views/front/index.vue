
<template>
  <div class="container">
    <frontHeader></frontHeader>
    <div class="main">
      <div class="search-area">
        <div class="title">
<!--          甘肃中医药大学论文提交系统-->
          xx 搜索
        </div>
        <div class="search">
          <el-form ref="form" :inline="true" :model="form">
            <el-form-item>
              <el-input v-model="form.text" style="width: 400px;"></el-input>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" >搜索</el-button>
            </el-form-item>
          </el-form>
        </div>
      </div>
    </div>


  </div>
</template>

<script>

  import frontHeader  from "./components/header";
  export default {
    name: 'front_index',
    components:{frontHeader},
    data() {
      return {
        isLogin:true,
        form: {
          text: '',
        },
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
    padding: 0;
    display: flex;
    flex-shrink: 0;
    box-sizing: border-box;
  }
  .main{
    display: flex;
    padding-top: 80px;
    flex-shrink: 0;
    height: 100%;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .search-area{
    width: 800px;
    height: 320px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .search-area .title{
    width: 800px;
    display: inherit;
    justify-content: center;
    height: 120px;
    align-items: center;
    font-size: 32px;
    letter-spacing: 0.25em;
  }
  .search-area .el-input__inner{
    border-color: #b0b0b0 ;
  }


</style>
