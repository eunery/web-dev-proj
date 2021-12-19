<template>
  <div class="slider">
    <div class="container">
      <Slider></Slider>
    </div>
  </div>
  <div class="main-content">
    <div class="container">
      <Content></Content>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Slider from '@/components/Slider.vue';
import Content from '@/components/Content.vue';

export default {
  name: 'Home',
  components: {
    Slider, Content,
  },
};
</script>
