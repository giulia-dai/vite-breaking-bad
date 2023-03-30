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
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(results => {
          this.store.cardList = results.data.data;
        });
    },
    getArchetypeCard() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(results => {
          this.store.archetypes = results.data;
        })
    },
    searchArchetype() {
      if (store.doSelect == '') {
        this.getCards();
      } else {
        let urlApi = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';
        urlApi += `?archetype=${this.store.doSelect}`;

        axios.get(urlApi)
          .then(results => {
            this.store.cardList = results.data.data;
          })
      }
    }
  },
  created() {
    this.getCards();
    this.getArchetypeCard();
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
        <AppSelect @changes="searchArchetype"></AppSelect>
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