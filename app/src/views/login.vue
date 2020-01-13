<template>
<el-scrollbar>
<div class="login">
    <div class="txt"><p>ele后台管理系统</p></div>
    <el-form
        :model="form" 
        :rules="rules"
        ref="form" 
        label-width="100px"
        >
<!-- 用户信息 -->
        <el-form-item
            label="用户"
            prop="name"
        >
            <el-input 
            v-model="form.name"
            auto-complete="off"
            placeholder="请输入用户名称">
            </el-input>
        </el-form-item>


<!-- 登录密码 -->
        <el-form-item
          label="密码"
          prop="pass"
        >
          <el-input
            type="password"
            v-model="form.pass"
            auto-complete="off"
            placeholder="请输入密码"
          ></el-input>
        </el-form-item>
        <el-row>
            <el-button 
            type="success"
            @click="submit"
            >登陆</el-button>
        </el-row>
        <div class="pp">
        <p>温馨提示:</p>
        <p>未登录过的新用户，自动注册</p>
        <p>注册过的用户可凭账号密码登录</p>   
        </div>
    </el-form>
</div>
</el-scrollbar>

</template>

<script>
    export default {
        name:'login',
        data() {
            return {
                form: {
                    name: '',
                    pass:'',
                },
                rules: {
                    name: [
                        { required: true, message: '请输入用户名称', trigger: 'blur' },
                        { min: 2, max: 8, message: '长度在 2 到 8 个字符', trigger: 'blur' }
                    ],
                    pass: [
                        { required: true, message: '请输入密码', trigger: 'blur' },
                        { min: 2, max: 8, message: '长度在 2 到 8 个字符', trigger: 'blur' }
                    ],
                }
            }
        },
        methods:{
            submit(){
         console.log(111)
                this.$refs.form.validate((valid)=>{
                    if(valid){
                        this.$message.success('登陆成功');
                        setTimeout(()=>{
                            this.$router.push('/home')
                        },2000)
                    }else{
                        this.$message.error('格式错误，请重新输入')
                    }
                })
            }
        }
    }
</script>

<style>
*{
    margin: 0;
    padding: 0;

}
.login{
    height: 100vh;
    background-color: #fffbf0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.el-form{
    height: 45px;
    width: 500px;
    background: #fffbf0;
    border-radius: 5px;
    padding: 50px 0;
}
.el-form-item {
    margin-bottom: 30px;
}
 .el-form-item.is-required:not(.is-no-asterisk)>.el-form-item__label:before {
    content: '';
}

.el-form-item__label {
    color: #F56C6C;
    background:#fffbf0;
    font-size: 18px;
}
.el-input__inner {
    width: 85%;
}
.el-scrollbar__wrap {
    overflow-x: hidden;
    overflow-y: hidden;
    background: #ffa631; 
}
.el-input {
    background:  #fffbf0;
    margin: auto;
}
.el-row{
    background: #fffbf0;
    display: flex;
    justify-content: center;
}
.el-button{
    width: 75%;
}
.el-button > span {
    background-color: #67C23A;
    border-color: #67C23A;
}
.login > .txt >p{
    color: #F56C6C;
    font-size: 38px;
    font-weight: 500;
    position: absolute;
    top: 35%;
    left: 40%;
}

.el-form-item__error{
    background:#fffbf0;
}


.pp>p{
    line-height: 14px; 
    padding: 2.5px 2px;
    text-align: center;
    font-size: 12px;
    color: #F56C6C;
    background: #fffbf0;
}
</style>