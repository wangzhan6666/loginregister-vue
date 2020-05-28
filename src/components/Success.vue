<template>
   <div style="text-align:center">
     登录成功！
     <img src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1588785777907&di=df2efd0ae3686a12f071ab67e3e00a2d&imgtype=0&src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20180523%2F93c796f46fd5417a9af7ba0b9ae87627.gif">
     <router-link to='/'>
       <span>返回首页</span>
     </router-link>
   </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data () {
    return {
      userName: "",
      password:""
    }
  },
  created(){

  },
  methods:{
    login: function(){
      let fd = new FormData();
      fd.append("userName",this.userName);
      fd.append("passwd",this.password);

      let config = {
        headers: {
          'Content-Type': 'multipart/form-data'
        }
      }

      this.$axios.post("user/login", fd, config).then( res => {
        alert(res.data.msg)
      }).catch( res => {
        alert(res.data.msg)
      })
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  body{
    background: #ebebeb;
    font-family: "Helvetica Neue","Hiragino Sans GB","Microsoft YaHei","\9ED1\4F53",Arial,sans-serif;
    color: #222;
    font-size: 12px;
  }
  *{padding: 0px;margin: 0px;}
  .top_div{
    background: #008ead;
    width: 100%;
    height: 400px;
  }
  .ipt{
    border: 1px solid #d3d3d3;
    padding: 10px 10px;
    width: 290px;
    border-radius: 4px;
    padding-left: 35px;
    -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075);
    box-shadow: inset 0 1px 1px rgba(0,0,0,.075);
    -webkit-transition: border-color ease-in-out .15s,-webkit-box-shadow ease-in-out .15s;
    -o-transition: border-color ease-in-out .15s,box-shadow ease-in-out .15s;
    transition: border-color ease-in-out .15s,box-shadow ease-in-out .15s
  }
  .ipt:focus{
    border-color: #66afe9;
    outline: 0;
    -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075),0 0 8px rgba(102,175,233,.6);
    box-shadow: inset 0 1px 1px rgba(0,0,0,.075),0 0 8px rgba(102,175,233,.6)
  }
  .u_logo{
    background: url("../assets/images/username.png") no-repeat;
    padding: 10px 10px;
    position: absolute;
    top: 43px;
    left: 40px;

  }
  .p_logo{
    background: url("../assets/images/password.png") no-repeat;
    padding: 10px 10px;
    position: absolute;
    top: 12px;
    left: 40px;
  }
  a{
    text-decoration: none;
  }
  .tou{
    background: url("../assets/images/tou.png") no-repeat;
    width: 97px;
    height: 92px;
    position: absolute;
    top: -87px;
    left: 140px;
  }
  .left_hand{
    background: url("../assets/images/left_hand.png") no-repeat;
    width: 32px;
    height: 37px;
    position: absolute;
    top: -38px;
    left: 150px;
  }
  .right_hand{
    background: url("../assets/images/right_hand.png") no-repeat;
    width: 32px;
    height: 37px;
    position: absolute;
    top: -38px;
    right: -64px;
  }
  .initial_left_hand{
    background: url("../assets/images/hand.png") no-repeat;
    width: 30px;
    height: 20px;
    position: absolute;
    top: -12px;
    left: 100px;
  }
  .initial_right_hand{
    background: url("../assets/images/hand.png") no-repeat;
    width: 30px;
    height: 20px;
    position: absolute;
    top: -12px;
    right: -112px;
  }
  .left_handing{
    background: url("../assets/images/left-handing.png") no-repeat;
    width: 30px;
    height: 20px;
    position: absolute;
    top: -24px;
    left: 139px;
  }
  .right_handinging{
    background: url("../assets/images/right_handing.png") no-repeat;
    width: 30px;
    height: 20px;
    position: absolute;
    top: -21px;
    left: 210px;
  }
  #loginBtn {
    margin-right: 30px;
    background: rgb(0, 142, 173);
    padding: 7px 10px;
    border-radius: 4px;
    border: 1px solid rgb(26, 117, 152);
    border-image: none;
    color: rgb(255, 255, 255);
    font-weight: bold;
    cursor: pointer;
  }

</style>
