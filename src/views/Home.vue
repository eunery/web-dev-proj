<template>
  <Slider></Slider>
  <Content></Content>
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
