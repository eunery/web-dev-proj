<template>
  <div class="add-post">
    <div class="container">
      <AddPost></AddPost>
    </div>
  </div>
</template>

<script>
import AddPost from '@/components/AddPost.vue';

export default {
  name: 'AdminPanel',
  components: {
    AddPost,
  },
};

</script>

<style scoped>

</style>
