<template>
  <the-header title='Books'></the-header>
  <the-books></the-books>
</template>

<script>

import TheHeader from '@/components/layouts/TheHeader.vue';
import TheBooks from '@/components/BookItems/TheBooks.vue';
export default {
  components: { TheHeader, TheBooks }
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