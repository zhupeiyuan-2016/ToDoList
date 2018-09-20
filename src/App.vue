<template>
  <div id="app">
    <div class = "header">
    <Row>
      <Col :xs="12":sm= "3" style="height:2rem" >
         <img class= "logo"  :src="logo" alt="" >
      </Col>
      <Col :xs="0" :sm= "3" >
         <h1 class = "title">{{title}}</h1>
      </Col>
      <Col :xs="12"  :sm= "18" >
         <Dropdown class ="login"> 
             <a href="javascript:void(0)" style="color:#fffffb">
             登录/注册
             <Icon type="ios-arrow-down"></Icon> </a>
             <DropdownMenu slot="list">
                 <DropdownItem>登录</DropdownItem>
                 <DropdownItem>注册</DropdownItem>
             </DropdownMenu>
         </Dropdown> 
      </Col>
    </Row>
    </div>
    <Row :gutter="20">
        <Col :xs="0" :sm="6">
            <div is = TreeList :data = "TreeListData"></div>
        </Col>
        <Col :xs="12" :sm="12">
            <div is = PostData ></div>
        </Col>
    </Row>
  </div>
</template>
<script>
import TreeList from './components/TreeList.vue'
import PostData from './components/PostData.vue'
import DataList from './components/DataList.vue'
export default{
    name:'home',
    components:{
        TreeList,
        PostData,
        DataList
  },
    data:function(){
        return{
            logo:'http://ouvyoji2r.bkt.clouddn.com/2017/09/3517137951.jpg',
            title:'萌日常',
            TreeListData:[
                {
                    id:1,
                    date:'1976年',
                    content:'开始'
                },
                {
                    id:2,
                    date:'2018',
                    content:'结束'
                }
            ]
    } 
  }
}
</script>
<style scoped>
.header{
    height:4rem;
    background-color:#7266ba;
}
.logo{
    height:2rem;
    width:2rem;
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
