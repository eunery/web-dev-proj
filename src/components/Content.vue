<template>
  <div class="table">
    <div class="table__header">
      <h2>5 шагов к заявке</h2>
    </div>
    <ul class="table__info">
      <li class="table__info__calc-icon">
        <img class="calc-icon__image"
             v-bind:src="require('../assets/images/Content/' + calcIcon)" />
        <h3>Расчетать стоимость</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info__car-icon">
        <img class="car-icon__image"
             v-bind:src="require('../assets/images/Content/' + carIcon)" />
        <h3>Вызвать курьера</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info__hand-coin-icon">
        <img class="hand-coin-icon__image"
             v-bind:src="require('../assets/images/Content/' + handCoinIcon)" />
        <h3>Оплатить услуги</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info__pageIcon">
        <img class="page-icon__image"
             v-bind:src="require('../assets/images/Content/' + pageIcon)" />
        <h3>Заключить договор</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info__passport-icon">
        <img class="passport-icon__image"
             v-bind:src="require('../assets/images/Content/' + passportIcon)" />
        <h3>Предоставить данные</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Content',
  data() {
    return {
      calcIcon: 'calcIcon.png',
      carIcon: 'carIcon.png',
      handCoinIcon: 'handCoinIcon.png',
      pageIcon: 'pageIcon.png',
      passportIcon: 'passportIcon.png',
    };
  },
};
</script>

<style lang="css" src="../../public/scss/Content.css" scoped>

</style>
