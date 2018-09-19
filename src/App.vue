<template>
  <div id="app">
    <div class = "header">
    <Row>
      <Col :xs="12":sm= "3" >
         <img class= "logo"  :src="logo" alt="" >
      </Col>
      <Col :xs="0" :sm= "3" >
         <h1 class = "title">{{title}}</h1>
      </Col>
      <Col :xs="12"  :sm= "18" >
         <Dropdown class ="login"> <a href="javascript:void(0)" style="color:#fffffb"> 登录/注册 <Icon type="ios-arrow-down"></Icon> </a> <DropdownMenu slot="list"> <DropdownItem>登录</DropdownItem> <DropdownItem>注册</DropdownItem> </DropdownMenu>
         </Dropdown> 
      </Col>
    </Row>
    </div>
  </div>
</template>
<script>
export default{
  name:'home',
  data:function(){
    return{
      logo:'http://ouvyoji2r.bkt.clouddn.com/2017/09/3517137951.jpg',
      title:'萌日常',
      value:''
    } 
  }
}
</script>
<style stoped>
.header{
    height:4rem;
    margin-bottom:1.8rem;
    background-color:#7266ba;
}
.logo{
    height:2.5rem;
    width:2.5rem;
    margin:1rem 2rem;
    border-radius:50%;
}
.title{
    font-size:1.4rem;
    color:#fffffb;
    margin:1rem 0rem;
}
.login{
    float:right;
    font-size:0.8rem;
    margin:1.5rem 2rem;
}
</style>
