<template>
  <the-header title='Books'></the-header>
  <stored-books :books='storedBooks'></stored-books>
</template>

<script>
import StoredBooks from '@/components/BookItems/StoredBooks.vue';
import TheHeader from '@/components/layouts/TheHeader.vue';
export default {
  components: { TheHeader, StoredBooks },
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

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

  * {
    box-sizing: border-box;
  }

  html {
    font-family: 'Roboto', sans-serif;
  }

  body {
  margin: 0;
  }
</style>