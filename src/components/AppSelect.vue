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
    <select name="archetype" id="archetype">
        <option value="archetype"></option>
    </select>
</template>

<style scoped lang="scss">
#archetype {
    margin: 5px 20px;
    border-radius: 20px;
    border: none;
    width: 100px;
    padding: 10px;
}
</style>