<template>
    <div id="app">
        <Header></Header>
        <Exposition msg="Welcome to Your Vue.js App" />
        <div id="grid">
            <Grid></Grid>
        </div>
    </div>
</template>

<script>
import Exposition from './components/Exposition.vue';
import Header from './components/Header.vue';
import Grid from './components/Grid.vue';

export default {
    name: 'app',
    components: {
        Exposition,
        Header,
        Grid,
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Russo+One&display=swap');
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

#grid {
    display: flex;
    justify-content: center;
}
</style>
