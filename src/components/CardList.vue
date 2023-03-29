<script>
import { store } from '../store.js';
import Card from './Card.vue';

export default {
    name: 'CardList',
    components: {
        Card
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <!-- ciclo per far apparire le card -->
    <div class="card-box" v-for="(single_card, i) in store.cardList" :key="i">
        <Card :image="single_card.card_images[0].image_url" :name="single_card.name" :type="single_card.archetype" />
    </div>
</template>

<style scoped></style>