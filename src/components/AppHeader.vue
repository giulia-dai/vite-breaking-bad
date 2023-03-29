<script>
export default {
    name: 'AppHeader',
    props: {
        title: String
    }
}
</script>

<template>
    <div class="wrapper">
        <img src="../assets/logo.jpg" alt="logo yu-gi-oh">
        <h1>{{ title }}</h1>
    </div>
</template>

<style lang="scss" scoped>
h1 {
    background-color: white;
    color: black;
    font-weight: 200;
    font-size: 50px;
    display: inline-block;
    vertical-align: middle;
}

img {
    width: 8%;
    vertical-align: middle;
}
</style>