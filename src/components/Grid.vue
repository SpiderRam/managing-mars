<template>
    <div id="gridWrapper">
        <div class="row single solid">
            <p>Click here to start a new game</p>
        </div>
        <div class="row">
            <Resource
                v-on:add-to-current="current += $event"
                filename="mars-plants.png"
                altText="Mars plant production symbol"
            ></Resource>
            <Resource
                v-on:add-to-current="current += $event"
                filename="mars-titanium.png"
                altText="Mars titanium production symbol"
            ></Resource>
        </div>
        <div class="row single">
            <div id="goal">
                <p>Goal: {{ goal }}</p>
                <p v-bind:style="{ color: currentColor }">
                    Current: {{ current }}
                </p>
            </div>
        </div>
        <div class="row">
            <Resource
                v-on:add-to-current="current += $event"
                filename="mars-heat.png"
                altText="Mars heat production symbol"
            ></Resource>
            <Resource
                v-on:add-to-current="current += $event"
                filename="mars-energy.png"
                altText="Mars energy production symbol"
            ></Resource>
        </div>
        <div class="row single solid">
            <ul>
                <li>Won: {{ gamesWon }}</li>
                <li>Lost: {{ gamesLost }}</li>
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
    data: function() {
        return {
            goal: Math.floor(Math.random() * 101 + 19),
            current: 0,
            status: 'ready',
            gamesWon: 0,
            gamesLost: 0,
            currentColor: 'green',
            gameOver: false,
            ready: true,
        };
    },
    watch: {
        current: function() {
            if (this.goal > this.current) {
                this.status = 'ready';
                this.currentColor = 'green';
            } else if (this.goal === this.current) {
                this.status = 'won';
                this.gamesWon += 1;
            } else {
                this.status = 'lost';
                this.currentColor = 'red';
                this.gamesLost += 1;
            }
        },
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
