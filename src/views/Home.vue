<template>
  <div class="home">
    <div>{{msg}}</div>
  </div>
</template>

<script>
// @ is an alias to /src
//import Header from '@/components/Header.vue'

export default {
  name: 'home',
  data:function(){
    return {
        msg:'主页' 
    } 
  }
}
</script>
