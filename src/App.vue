<script>
import AppHeader from './components/AppHeader.vue';
import axios from 'axios';
import { store } from './store.js';

export default {
  components: {
    AppHeader,
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getCards() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?name=Dark Magician')
        .then(results => {
          this.store.cardList = results.data.results;
        });
    }
  },
  created() {
    this.getCards();
  }
}
</script>

<template>
  <header>
    <AppHeader title="Yu-Gi-Oh Api"></AppHeader>
  </header>

  <main>

  </main>
</template>

<style lang="scss" scoped>
main {
  background-color: #D48F38;
}
</style>