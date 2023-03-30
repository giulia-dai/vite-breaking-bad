<script>
import { store } from '../store';
export default {
    name: 'AppSelect',
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <select id="archetype" @change="$emit('changes')" v-model="store.doSelect">
        <option value="" selected>trova per archetipo</option>
        <option value="archetype" v-for="(archetype, i) in store.archetypes" :key="i">
            {{ archetype.archetype_name }}
        </option>
    </select>
</template>

<style scoped lang="scss">
#archetype {
    margin: 5px 10px;
    border-radius: 20px;
    border: none;
    width: 150px;
    padding: 10px;
}

span {
    margin: 5px;
}
</style>