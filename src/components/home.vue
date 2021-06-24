<template>
  <swiper :pagination="true" class="mySwiper mb-5">
    <swiper-slide><img src="image/01banner.jpg" alt=""></swiper-slide>
    <swiper-slide><img src="image/02banner.jpg" alt=""></swiper-slide>
    <swiper-slide><img src="image/03banner.jpg" alt=""></swiper-slide>
  </swiper>
  <div class="best">
  <div class="container mb-5">
    <h2>BEST</h2>
    <p>천만펫의 트렌드가 시작되는 BITE ME</p>
    <div class="row mb-5">
      <div class="col-sm-6 col-md-3" v-for="(item,i) in 4" :key="i">
        <img :src="pdata[i].image" alt="" class="w-100">
         <div @click="$emit('pOpen',pdata[i].id)">{{pdata[i].title}}</div> 
      </div>
    </div>

    <div class="btn m-auto d-block" style="width:100px">
      <router-link to="/product">MORE</router-link>
    </div>
  </div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import "swiper/components/pagination/pagination.min.css"
import 'swiper/swiper.scss';

// import Swiper core and required modules
import SwiperCore, {
  Pagination
} from 'swiper/core';

// install Swiper modules
SwiperCore.use([Pagination]);

export default {
  props:['pdata'],
  components: {
    Swiper,
    SwiperSlide,
  },
}
</script>

<style>

.swiper-container {
  width: 100%;
  height: 100%;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: #fff;

  /* Center slide text vertically */
  display: -webkit-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.best h2 {text-align: center;} 
.best h2:after {content:""; width: 30px; height: 1px; background: #333;
                display: block; margin: 10px auto;}
.best p {text-align:center}
.best .row .t_txt {text-align: center;}
.best .row .p_txt {text-align: center;}
.best .btn {background: #ff6c2b;}
.best .btn a {color:#fff}
</style>