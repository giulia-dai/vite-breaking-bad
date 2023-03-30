<script>
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import AppSelect from './components/AppSelect.vue';
import axios from 'axios';
import { store } from './store.js';

export default {
  components: {
    AppHeader,
    CardList,
    AppSelect
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getCards() {
      // api per avere l'array di TUTTE le carte
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then(results => {
          this.store.cardList = results.data.data;
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
    <div class="container">
      <div class="ms_select">
        <AppSelect></AppSelect>
      </div>
      <div class="row">
        <CardList></CardList>
      </div>
    </div>

  </main>
</template>

<style lang="scss" >
@use './styles/general.scss';
</style>