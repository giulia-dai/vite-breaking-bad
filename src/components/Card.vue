<script>
export default {
    name: 'Card',
    props: {
        image: String,
        name: String,
        type: String
    }
}
</script>
<template>
    <div class="card">
        <img :src="image" />
        <h4 class="title">{{ name }}</h4>
        <h4 class="subtitle">{{ type }}</h4>
    </div>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card {
    width: 200px;
    height: 400px;
    text-align: center;
    background-color: $primary-color;
    margin: 10px;
}

img {
    width: 100%;
}

.title {
    padding: 5px;
    color: white;
    text-transform: uppercase;
    cursor: pointer;

    &:hover {
        text-decoration: underline;
    }

    &:active {
        color: red;
    }
}

.subtitle {
    font-weight: 100;
    padding: 20px 0;
    cursor: pointer;
}
</style>