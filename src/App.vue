<template>
  <div class="content">

    <header>
      <div class="container">
        <HeaderMenu></HeaderMenu>
      </div>
    </header>

    <main>
      <div class="container">
        <router-view/>
      </div>
    </main>

    <footer>
      <div class="container">
        <FooterMenu></FooterMenu>
      </div>
    </footer>

  </div>
</template>

<style lang="css">
@import "../public/scss/App.css";
@import "../public/reset.css";

</style>
<script>
import HeaderMenu from '@/components/Header-menu.vue';
import FooterMenu from '@/components/Footer-menu.vue';

export default {
  components: {
    HeaderMenu, FooterMenu,
  },
};
</script>
