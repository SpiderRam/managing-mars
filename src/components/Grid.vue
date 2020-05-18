<template>
    <div id="wrapper">
        <div class="row">
            <Resource
                filename="mars-plants.png"
                altText="Mars plant production symbol"
            ></Resource>
            <Resource
                filename="mars-titanium.png"
                altText="Mars titanium production symbol"
            ></Resource>
        </div>
        <div class="row single">
            <div id="goal">
                <p>Goal: 64</p>
                <p>Current: 64</p>
            </div>
        </div>
        <div class="row">
            <Resource
                filename="mars-heat.png"
                altText="Mars heat production symbol"
            ></Resource>
            <Resource
                filename="mars-energy.png"
                altText="Mars energy production symbol"
            ></Resource>
        </div>
    </div>
</template>

<script>
import Resource from './Resource.vue';

export default {
    components: {
        Resource,
    },
};
</script>

<style scoped>
.row {
    display: flex;
    width: 360px;
    justify-content: space-between;
    flex-flow: row nowrap;
    padding: 20px 0;
}

.row.single {
    justify-content: center;
}

#goal {
    height: 86px;
    font-family: 'Russo One', sans-serif;
}
</style>
