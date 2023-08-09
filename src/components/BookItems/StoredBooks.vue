<template>
  <ul>
    <book-item v-for='book in books'
               :key='book.id'
               :title='book.title'
               :description='book.description'
               :link='book.link'
    ></book-item>
  </ul>
</template>
<script>
import BookItem from '@/components/BookItems/BookItem.vue';

export default {
  props: ['books'],
  components: {
    BookItem
  }
}
</script>
<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>