<template>

  <div class="container mt-5 mb-5">
    <h2>PRODUCT</h2>
    <p>천만펫의 트렌드가 시작되는 BITE ME</p>
    <div class="row">
        <div class="col-sm-6 col-md-3" v-for="(item,i) in pdata" :key="i">
          <img :src="pdata[i].image" alt="" class="w-100">
        <div class="t_txt">{{pdata[i].title}}</div>
        <div class="p_txt">{{pdata[i].price}}</div>      
        </div>

    </div>
  </div>

</template>

<script>
export default {
  name:'product',
  props:['pdata'],
}
</script>

<style>
h2 {text-align: center;} 
h2:after {content:""; width: 30px; height: 1px; background: #333;
          display: block; margin: 10px auto;}
p {text-align:center}

.row .t_txt {text-align: center;}
.row .p_txt {text-align: center;}
</style>