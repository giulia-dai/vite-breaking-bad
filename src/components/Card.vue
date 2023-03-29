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
    <div class="wrap">
        <div class="card">
            <img :src="image" />
            <h4>{{ name }}</h4>
            <h5>{{ type }}</h5>
        </div>
    </div>
</template>
<style>
.card {
    width: 200px;
    text-align: center;
    background-color: #D48F38;
}

img {
    width: 100%;
}

.wrap {
    display: flex;
}
</style>