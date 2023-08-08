<template>
  <ul>
    <book-item v-for='book in storedBooks'
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
  components: { BookItem },
  data() {
    return {
      storedBooks: [
        {
          id: 'first-book',
          title: 'First Book',
          description: 'The first added book.',
          link: 'https://vuejs.org'
        },
        {
          id: 'second-book',
          title: 'Second Book',
          description: 'The second added book.',
          link: 'https://vuejs.org'
        }
      ]
    };
  }
};
</script>