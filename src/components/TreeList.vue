<template>
    <div class="root">
        <div class="TimeItem">
        <Timeline>
             <TimelineItem v-for="(item ,index) in data">
                 <p class="time" >{{item.date}}</p>
                 <p class="content">{{item.content}}</p>
             </TimelineItem>
             <TimelineItem>
                 <a href="#">查看更多</a>
             </TimelineItem>
        </Timeline> 
        </div>
        <div class="story">
            <p class="yiyang">{{yiyang}}</p>
        </div>
    </div>
</template>
<script>
export default{
    name:'TreeList',
    props:['data'],
    data:function(){
        return{
            msg:'TreeList',
            yiyang:'昨夜观天象,今面朝东南向写bug少'
        } 
    }
}
</script>
<style scoped>
.root{
    height:100vh;
    background-color:#3a3f51;
    color:white;
}        
.TimeItem{
    padding:3rem;
    float:left
}
.time{
    font-size: 14px;
    font-weight: bold;
}
.content{
    padding-left: 5px;
}
.story{
    float:right;
    width:1.3rem;
    padding:3rem 3rem 3rem 2rem;
    font-size:0.94rem;
    border-left:2px solid #494e8f;
}
</style>
