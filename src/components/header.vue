<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <router-link to="/" class="navbar-brand mr-5">BITE ME</router-link>

  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav">
      <li v-for="(item,i) in menu" :key="i" class="mr-5">
          <router-link :to="menu[i].link"> {{menu[i].title}} </router-link>
      </li>
    </ul>
  </div>
</nav>

  <!-- <ul class="menu clearfix">
      <li v-for="(item,i) in menu" :key="i">
          <router-link :to="menu[i].link"> {{menu[i].title}} </router-link>
      </li>
  </ul> -->
</template>

<script>
export default {
    name:'header',
    data(){
        return{
            menu:[
                {title:'home',link:'/'},
                {title:'company',link:'/company'},
                {title:'product',link:'/product'}
            ]
        }
    },
    methods:{
      close:function(){
        document.getElementById("navbarNav").classList.remove("show");
      }
    }

}
</script>

<style>

</style>