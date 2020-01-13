<template>
  <div>
    <el-container style="height:100vh">
        <el-header>
          <el-row >
              <el-col :span="8"><div class="grid-content bg-purple1"><span>后台管理系统</span></div></el-col>
              <el-col :span="8"><div class="grid-content bg-purple-light"></div></el-col>
              <el-col :span="8"><div class="grid-content bg-purple">
                <span></span><span></span><span></span>
                <span>欢迎凯宝登陆!</span>
              <el-button>退出</el-button>  
              </div></el-col>
          </el-row>
        </el-header>
            <el-container>
                <el-aside width="200px">
                  <leftMenu/>
                </el-aside>
            <el-main>
              主体
            </el-main>
        </el-container>
  </el-container>
  </div>
</template>

<script>
import leftMenu from './leftMenu';
  export default {
    name:'home',
    components:{
      leftMenu,
    }
  }
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
  .el-header{
    background-color: #ffab31;
    color:#fffbf0;
    text-align: center; 
    line-height: 60px;
  }
  .el-aside {
    background-color: #f0fcff;
    color: #f56c6c;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-row {
    height: 60px; 
    display: flex;
    align-items: center;
    justify-content: space-around;
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #ccc;
  }
  .bg-purple1 {
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  .bg-purple1 >span{
    color: #fffbf0;
    font-size: 28px;
    font-weight: 350;
  }
  .bg-purple {
    /* background: #666; */
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .bg-purple>span{
    font-size: 20px;
    font-weight: normal;
    color: #fffbf0;
    letter-spacing: 2px;
  }


.bg-purple>.el-button {
    width: 80px;
    color: #f56c6c;
    font-size: 16px;
    background-color: #fffbf0;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>
