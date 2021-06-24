<template>

    <top-header />
  <router-view :pdata="pdata"
  @pOpen="pView=true;pNum=$event">
  </router-view>

  <transition name="fade" style="position:relative;z-index:1000">
    <pPop :pdata="pdata" :pView="pView" :pNum="pNum" @pClose="pView=false"/>
  </transition>

    <bottom-footer />

</template>

<script>
import header from './components/header.vue'
import pdata from './pdata.js'
import pPop from './components/pPop.vue'
import footer from './components/footer.vue'
export default {
  name:'app',
  components:{
     'top-header':header,
      pPop:pPop,
     'bottom-footer':footer,
  },
  data(){
    return {
      pdata:pdata,
      pView:false,
      pNum:0
    }
  }
}
</script>

<style>
  *{margin:0; padding: 0;}
  li{list-style: none;}
  a:link,a:visited {text-decoration: none; color:#333}
  .clearfix:after{content:""; 
                  display: block; 
                  clear:both;}

  h1{text-align: center;}
  .menu li {float:left; width: calc(100%/3);}
  .menu li a {display: block; line-height: 40px; 
              background: slateblue; text-align: center;
              color:#fff} 
  .menu li a:hover {background: plum;}

  .pPop{position: fixed;z-index:10;
        background:#fff; width: 80%;
        top:50%;left:50%;
        transform:translate(-50%,-50%);
        box-shadow:0 0 10px rgba(0,0,0,0.5);    border-radius:10px;padding:20px}

  .fade-enter-from{opacity:0}
  .fade-enter-active{transition:0.5s}
  .fade-enter-to{opacity:1}

  .fade-leave-from{opacity:1}
  .fade-leave-active{transition:0.5s}
  .fade-leave-to{opacity:0}

  @media screen and (min-width:900px){
    .pPop{width: 800px;}
  }

</style>