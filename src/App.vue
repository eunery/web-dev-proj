<template>
  <div class="wrapper">
    <div class="modal" ref="modalbox">
      <div class="modal__content">
          <div class="modal__content__container">
            <div class="modal__button_close" v-on:click="CloseWindow">
              <img src="@/assets/images/ModalBox/Shape.png" />
            </div>
            <div class="modal__content_header">
              <h1>Авторизация</h1>
              <p>Введите логин и пароль, чтобы войти в личный кабинет</p>
            </div>
            <form class="modal__form" ref="form" @submit.prevent="validateForm">
              <div class="form__inputs">
                <input class="form__inputs_login" type="email" placeholder="Логин">
                <input class="form__inputs_password" type="password" placeholder="Пароль">
              </div>
              <input class="form__inputs_enter-button" type="submit" value="Войти">
            </form>
          </div>
      </div>
    </div>

    <header>
      <div class="header-menu">
        <div class="container">
          <HeaderMenu></HeaderMenu>
        </div>
      </div>
    </header>

    <main>
        <router-view></router-view>
    </main>

    <footer>
      <div class="footer-menu">
        <div class="container">
          <FooterMenu></FooterMenu>
        </div>
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
  methods: {
    CloseWindow() {
      const modalWindow = this.$refs.modalbox;
      modalWindow.style.display = 'none';
    },
    validateForm() {
      if (/^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
        .test(this.email)) {
        console.log('invalid');
      } else {
        this.$refs.form.submit();
      }
    },
  },
};
</script>
