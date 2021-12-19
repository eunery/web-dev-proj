<template>
<div class="header-slider">
  <div class="header-slider_container" ref="container">
   <div class="header-slider_list" ref="list">
     <div class="header-slider__item" ref="item">
       <div class="item__text">
         <h1>
           Срочная доставка день в день
         </h1>
         <p>
           Для тех, кто не может ждать у нас есть услуга
           срочной курьерской доставки корреспондеции и других видов отправлений.
         </p>
         <a class="delivery-link" href="">
           Заказать доставку
         </a>
       </div>
       <div class="item__image">
         <img src="@/assets/images/Slider/car.png" alt="">
       </div>
     </div>
     <div class="header-slider__item" ref="item">
       <div class="item__text">
         <h1>
           Подписание договора за 1 час
         </h1>
         <p>
           В течение часа наш курьер заберет
           вашу посылку и подпишет с Вами договор о предоставлении услуг.
         </p>
         <a class="delivery-link" href="">
           Заказать доставку
         </a>
       </div>
       <div class="item__image page">
         <img src="@/assets/images/Slider/page.png" alt="">
       </div>
     </div>
   </div>
  </div>
  <div class="slider-control" ref="controlBtn">
    <ul class="slider-control__list-slider-box" ref="controlList">
      <li class="list-slider-box_button" ref="btnPrev"></li>
      <li class="list-slider-box_button" ref="btnNext"></li>
    </ul>
  </div>
</div>
</template>

<script>
export default {
  name: 'Slider',
  methods: {
    SliderFunc() {
      const sliderContainer = this.$refs.container;
      const itemList = this.$refs.list;
      let items = this.$refs.list.children;
      const prev = this.$refs.btnPrev;
      const next = this.$refs.btnNext;
      const buttons = this.$refs.controlBtn;

      const trst = 1.5;
      const interval = 6000;
      let index = 0;
      let slideId;

      const firstClone = items[0].cloneNode(true);
      const lastClone = items[items.length - 1].cloneNode(true);
      firstClone.id = 'firstItem';
      lastClone.id = 'lastItem';
      itemList.append(firstClone);
      itemList.prepend(lastClone);
      const slideWidth = items[index].clientWidth;
      // const slideWidth = `${document.querySelector('.slider').clientWidth}`;
      // itemList.style.transform = `translateX(${-slideWidth * index * 2}px)`;

      const firstActive = () => {
        prev.classList.add('active');
        next.classList.remove('active');
      };
      const lastActive = () => {
        next.classList.add('active');
        prev.classList.remove('active');
      };

      const getItems = () => this.$refs.list.children;

      // next or prev slide
      const moveToPrevSlide = () => {
        items = getItems();
        if (index <= 1) {
          return;
        }
        index -= 1;
        itemList.style.transform = `translateX(${-slideWidth * index * 2}px)`;
      };
      const moveToNextSlide = () => {
        items = getItems();
        if (index >= items.length - 1) {
          return;
        }
        index += 1;
        if ((index % 2) === 0) {
          lastActive();
        } else {
          firstActive();
        }
        itemList.style.transform = `translateX(${-slideWidth * index * 2}px)`;
        itemList.style.transition = `${trst}s`;
      };
      // step interval
      const startSlide = () => {
        slideId = setInterval(() => {
          moveToNextSlide();
        }, interval);
      };
      // check last slide
      itemList.addEventListener('transitionend', () => {
        items = getItems();
        if (items[index].id === firstClone.id) {
          itemList.style.transition = 'none';
          index = 1;
          itemList.style.transform = `translateX(${-slideWidth * index * 2}px)`;
        }
      });
      // mouseover = stop, mouseout = continue
      sliderContainer.addEventListener('mouseover', () => {
        clearInterval(slideId);
      });
      sliderContainer.addEventListener('mouseout', startSlide);

      buttons.addEventListener('mouseover', () => {
        clearInterval(slideId);
      });
      buttons.addEventListener('mouseout', startSlide);
      // moving, buttons class active
      next.addEventListener('click', () => {
        if (index >= items.length - 2) {
          return;
        }
        moveToNextSlide();
        lastActive();
      });
      prev.addEventListener('click', () => {
        moveToPrevSlide();
        firstActive();
      });

      startSlide();
    },
  },
  mounted() {
    this.$refs.controlList.children[0].classList.add('active');
    this.SliderFunc();
  },
};
</script>

<style src="../../public/scss/Slider.css" scoped>

</style>
