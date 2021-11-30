<template>
  <div class="field">
    <div class="field__nav-menu field__nav-menu_left">
      <div class="field__nav-menu_link-logo">
        <a ref="">
          <img src="@/assets/images/Header-footer/logoAndName.svg" alt="" />
        </a>
      </div>
      <div class="field__nav-menu_description">
        <span>Курьерская служба доставки</span>
      </div>
    </div>
    <div class="field__nav-menu header__nav-menu_right">
      <div class="field__nav-menu_link-logo">
        <img src="@/assets/images/Header-footer/phoneIcon.svg" alt="" />
        <span> 8 (909) 023-12-51</span>
      </div>
      <div class="field__nav-menu_enter-link">
        <a class="link" ref="">Вход</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header-menu',
};
</script>

<style lang="css" src="../../public/scss/Header-menu.css" scoped>

</style>
