<template>
  <form class="add-post__form" ref="addpost" @submit.prevent="validatePost">
    <div class="add-post__header">
      <h1>Добавить новость</h1>
      <p>Введите текст новости, а также приложите изображение
        (размер: 270х270px, формат JPG,PNG)</p>
    </div>
    <div class="add-post__input">
      <textarea class="add-post__textarea"
                ref="textarea" @keyup="countSymbols" @keydown="countSymbols"
                placeholder="Введите текст новости" ></textarea>
      <div class="input__count">
        <p class="input__count_text">
          Символов:
          <span class="input__count_red-text" ref="redspan">{{symbols}}</span>
          /150
        </p>
      </div>
    </div>
    <div class="add-image">
      <img class="add-image__logo" src="@/assets/images/AddPost/Shape.png" alt="" />
      <input class="add-image__input" type="file" @click="clearImageData"
             @change="previewImage" accept="image/*"/>
      <div class="preview" v-if="imageData.length > 0">
        <img class="preview__image" :src="imageData" alt="">
        <div class="preview__path">
          <h1 class="path__header">{{ imagePath }}
            <img class="header__close-button" src="@/assets/images/ModalBox/Shape.png"
                 @click="clearImageData" alt=""/>
          </h1>
        </div>
      </div>
      <div class="error" v-if="isNotValidType" ref="errorType">
        <p class="error__text">Неверный формат изображения</p>
      </div>
      <div class="error" v-if="isFieldFull">
        <p class="error__text">Превышен лимит символов</p>
      </div>
      <div class="error" v-if="isFieldEmpty">
        <p class="error__text">Введите текст</p>
      </div>
    </div>
    <div class="add-post__form__submit">
      <input class="add-post__form__submit_button" type="submit" value="Применить"/>
    </div>
  </form>
</template>

<script>
export default {
  name: 'AddPost',
  data() {
    return {
      imagePath: '',
      imageData: '',
      symbols: 0,
      isNotValidType: false,
      isFieldFull: false,
      isFieldEmpty: false,
    };
  },
  mounted() {
    document.querySelector('.field').classList.add('admin');
  },
  methods: {
    validatePost() {
      this.isNotValidType = false;
      this.isFieldFull = false;
      this.isFieldEmpty = false;
      if (this.symbols > 150) {
        this.isFieldFull = true;
      } else if (this.symbols === 0) {
        this.isFieldEmpty = true;
      } else {
        this.$refs.addpost.submit();
      }
    },
    countSymbols() {
      const span = this.$refs.redspan;
      const area = this.$refs.textarea;
      this.symbols = this.$refs.textarea.textLength;
      if (this.symbols > 150) {
        span.style.color = '#FF2323';
      }
      area.classList.remove('red');
    },
    clearImageData() {
      this.imageData = '';
    },
    previewImage(event) {
      const input = event.target;
      this.isNotValidType = false;
      if (input.files && input.files[0]) {
        const fileExtension = input.files[0].name.split('.').pop().toLowerCase();
        if (!((fileExtension === 'png') || (fileExtension === 'jpg'))) {
          this.isNotValidType = true;
          return;
        }
        const reader = new FileReader();
        reader.onload = (e) => {
          this.imageData = e.target.result;
        };
        reader.readAsDataURL(input.files[0]);
        this.imagePath = input.files[0].name;
      }
    },
  },
};
</script>

<style src="../../public/scss/AddPost.css" lang="css" scoped>

</style>
