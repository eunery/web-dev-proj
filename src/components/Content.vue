<template>
  <div class="table">
    <div class="table_header">
      <h2>5 шагов к заявке</h2>
    </div>
    <ul class="table__info">
      <li class="table__info_calcIcon">
        <img class="calcIcon"
             v-bind:src="require('../assets/images/Content/' + calcIcon)" />
        <h3>Расчетать стоимость</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info_carIcon">
        <img class="carIcon"
             v-bind:src="require('../assets/images/Content/' + carIcon)" />
        <h3>Вызвать курьера</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info_handCoinIcon">
        <img class="handCoinIcon"
             v-bind:src="require('../assets/images/Content/' + handCoinIcon)" />
        <h3>Оплатить услуги</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info_pageIcon">
        <img class="pageIcon"
             v-bind:src="require('../assets/images/Content/' + pageIcon)" />
        <h3>Заключить договор</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elitsequi nesciunt.</p>
      </li>
      <li class="table__info_passportIcon">
        <img class="passportIcon"
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
