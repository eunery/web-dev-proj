<template>
  <div class="field" ref="field">
    <div class="field__nav-menu field__nav-menu_left">
      <div class="field__nav-menu__logo">
          <a href="/">
            <img src="@/assets/images/Header-footer/logoAndName.svg" alt="" />
          </a>
        </div>
      <div class="field__nav-menu__description">
          <div class="text">Курьерская служба доставки</div>
        </div>
    </div>
    <div class="field__nav-menu header__nav-menu_right">
      <div class="field__nav-menu_phone">
          <img class="phone__image" src="@/assets/images/Header-footer/phoneIcon.svg" alt="" />
          <div class="phone__number"> 8 (909) 023-12-51</div>
        </div>
      <div class="field__nav-menu__enter-link">
          <a class="enter-link" href="#" v-on:click="modalBox" ref="link">Вход</a>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header-menu',
  methods: {
    modalBox() {
      const box = this.$parent.$refs.modalbox;
      box.style.display = 'block';
    },
  },
};
</script>

<style lang="css" src="../../public/scss/Header-menu.css" scoped>

</style>
