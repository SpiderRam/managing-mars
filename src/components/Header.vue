<template>
    <div class="header"></div>
</template>

<script>
export default {
    name: 'app',
    data() {
        return {};
    },
    methods: {},
};
</script>

<style scoped>
.header {
    font-family: 'Russo One', sans-serif;
    margin-bottom: 5%;
    background-image: url('../assets/terraforming-mars.jpg');
    text-shadow: 1px 1px 2px black, 0 0 25px lemonchiffon, 0 0 5px lawngreen;
    background-size: cover;
    width: 100vw;
    display: flex;
    flex: row nowrap;
    height: 200px;
}
.title {
    font-size: 4em;
}
.innerContainer {
    margin: 0 3vw;
}
.subtitle {
    font-size: 2em;
}
</style>
