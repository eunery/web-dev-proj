<template>
  <div class="info-menu">
    <ul class="info-menu__nav-menu">
      <li class="info-menu__nav-menu__logo">
        <a href="/">
          <img src="@/assets/images/Header-footer/logoAndName.svg" alt="" />
        </a>
      </li>
      <li class="info-menu__nav-menu__client">
        <a href="/">
          О компании<br/>
        </a>
        <a href="/">
          Вакансии<br/>
        </a>
        <a href="/">
          Клиенту<br/>
        </a>
        <a href="/">
          Франчайзинг<br/>
        </a>
      </li>
      <li class="info-menu__nav-menu__delivery">
        <a href="/">
          Доставка из Китая<br/>
        </a>
        <a href="/">
          Все услуги<br/>
        </a>
        <a href="/">
          Акции<br/>
        </a>
      </li>
      <li class="info-menu__nav-menu__address">
        <h2>
          manager@uexpress.ru
          <br>
          <br>
          115221, г. Челябинск,
          ул. Северная, д. 29-в
          <br>
          <br>
          Мы работаем по 24 часа
          5 дней в неделю
        </h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Footer-menu',
  mounted() {
    document.querySelector('.info-menu').classList.add('admin');
  },
};
</script>

<style src="../../public/scss/Footer-menu.css" lang="css" scoped>

</style>
