<template>
<div class="header-slider">
  <div class="header-slider_container" ref="container">
   <div class="header-slider_track" ref="track">
     <div class="header-slider__item" ref="item">
       <div class="header-slider__text">
         <h1>
           Срочная доставка день в день
         </h1>
         <p>
           Для тех, кто не может ждать у нас есть услуга
           срочной курьерской доставки корреспондеции и других видов отправлений.
         </p>
         <a class="link" href="">
           Заказать доставку
         </a>
       </div>
       <div class="header-slider__img">
         <img src="@/assets/images/Slider/car.png" alt="">
       </div>
     </div>
     <div class="header-slider__item" ref="item">
       <div class="header-slider__text">
         <h1>
           Подписание договора за 1 час
         </h1>
         <p>
           В течение часа наш курьер заберет
           вашу посылку и подпишет с Вами договор о предоставлении услуг.
         </p>
         <a class="link" href="">
           Заказать доставку
         </a>
       </div>
       <div class="header-slider__img">
         <img src="@/assets/images/Slider/page.png" alt="">
       </div>
     </div>
   </div>
  </div>
  <div class="slider-control">
    <ul class="slider-control__list-slider-box">
      <li class="slider-control__list-slider-box_slider-box" ref="btnPrev" @click="ready"></li>
      <li class="slider-control__list-slider-box_slider-box" ref="btnNext" @click="clickNext"></li>
    </ul>
  </div>
</div>
</template>

<script>
export default {
  name: 'Slider',
  methods: {
  },
};
// function ready() {
//   let position = 0;
//   const slidesToShow = 1;
//   const slidesToScroll = 1;
//   const { container } = this.$refs;
//   const track = this.$refs.track;
//   const { item } = this.$refs;
//   const btnPrev = this.$refs.btnPrev;
//   const btnNext = this.$refs.btnNext;
//   const itemWidth = container.width() / slidesToShow;
//
//   for (const index of item) {
//     index.css({
//       minWidth: itemWidth,
//     });
//   }
// }
// ready();

</script>

<style src="../../public/scss/Slider.css" scoped>

</style>
