<template>
  <base-card>
    <base-button @click='setSelectedTab("stored-books")' :mode='storedBookButtonMode' >Stored Books</base-button>
    <base-button @click='setSelectedTab("add-books")' :mode='addBookButtonMode'>Add Book</base-button>
  </base-card>
  <keep-alive>
    <component :is='selectedTab'></component>
  </keep-alive>
</template>

<script>
import StoredBooks from '@/components/BookItems/StoredBooks.vue';
import AddBooks from '@/components/BookItems/AddBooks.vue';
export default {
  components: { StoredBooks, AddBooks},
  data() {
    return {
      selectedTab: 'stored-books',
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
  },
  provide() {
    return {
      books: this.storedBooks,
      addBook: this.addBook,
      removeBook: this.removeBook
    }
  },
  computed: {
    storedBookButtonMode() {
      return this.selectedTab === "stored-books" ? null : "flat";
    },
    addBookButtonMode() {
      return this.selectedTab === "add-books" ? null : "flat";
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addBook(title, description, url) {
      const newBook = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: url
      }
      this.storedBooks.unshift(newBook);
      this.selectedTab = 'stored-books';
    },
    removeBook(bookId) {
      const bookIndex = this.storedBooks.findIndex(book => book.id === bookId);
      this.storedBooks.splice(bookIndex, 1);
    }
  }
}
</script>