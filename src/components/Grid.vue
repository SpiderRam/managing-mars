<template>
    <div id="gridWrapper">
        <div class="row single solid">
            <p>Click here to start a new game</p>
        </div>
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
        <div class="row single solid">
            <ul>
                <li>Won: 1</li>
                <li>Lost: 47</li>
            </ul>
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
#gridWrapper {
    margin: 10px 0;
    border-left: 1px solid #2c3e50;
    border-right: 1px solid #2c3e50;
}
.row {
    display: flex;
    width: 340px;
    justify-content: space-between;
    flex-flow: row nowrap;
    padding: 20px 10px;
    font-family: 'Russo One', sans-serif;
}

.row.single {
    justify-content: center;
}

.row.solid {
    color: white;
    background-color: #2c3e50;
    cursor: pointer;
}

#goal {
    height: 86px;
}

ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
</style>
