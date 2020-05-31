<template>
    <div id="gridWrapper">
        <div class="row single solid top" @click="startNewGame">
            <p>Click here to start a new game</p>
        </div>
        <div class="row">
            <template v-for="(resource, x) in row1">
                <Resource
                    :key="x"
                    v-if="status === 'ready'"
                    v-bind:resourceVal="resource.val"
                    v-on:add-to-current="addResource"
                    v-bind:filename="resource.filename"
                    v-bind:altText="resource.altText"
                ></Resource>
                <Resource
                    v-else
                    :key="x"
                    v-bind:filename="resource.filename"
                    v-bind:altText="resource.altText"
                ></Resource>
            </template>
        </div>
        <div class="row single">
            <div v-if="status === 'new'" id="goal"></div>
            <div v-else id="goal">
                <p>Goal: {{ goal }}</p>
                <p
                    v-if="status === 'ready'"
                    v-bind:style="{ color: currentColor }"
                >
                    Current: {{ current }}
                </p>
                <p
                    v-else-if="status === 'won'"
                    v-bind:style="{ color: currentColor }"
                >
                    Winner! {{ current }}
                </p>
                <p
                    v-else-if="status === 'lost'"
                    v-bind:style="{ color: currentColor }"
                >
                    Too bad.... {{ current }}
                </p>
            </div>
        </div>
        <div class="row">
            <template v-for="(resource, x) in row2">
                <Resource
                    :key="x"
                    v-if="status === 'ready'"
                    v-bind:resourceVal="resource.val"
                    v-on:add-to-current="addResource"
                    v-bind:filename="resource.filename"
                    v-bind:altText="resource.altText"
                ></Resource>
                <Resource
                    v-else
                    :key="x"
                    v-bind:filename="resource.filename"
                    v-bind:altText="resource.altText"
                ></Resource>
            </template>
        </div>
        <div class="row single solid bottom">
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
            goal: Number,
            current: Number,
            status: 'new',
            gamesWon: 0,
            gamesLost: 0,
            currentColor: 'green',
            row1: [
                {
                    filename: 'mars-plants.png',
                    altText: 'Mars plant production symbol',
                    val: Math.floor(Math.random() * 11 + 1),
                },
                {
                    filename: 'mars-titanium.png',
                    altText: 'Mars titanium production symbol',
                    val: Math.floor(Math.random() * 11 + 1),
                },
            ],
            row2: [
                {
                    filename: 'mars-heat.png',
                    altText: 'Mars heat production symbol',
                    val: Math.floor(Math.random() * 11 + 1),
                },
                {
                    filename: 'mars-energy.png',
                    altText: 'Mars energy production symbol',
                    val: Math.floor(Math.random() * 11 + 1),
                },
            ],
        };
    },
    methods: {
        addResource: function(event) {
            this.current += event;
        },
        startNewGame: function() {
            this.current = 0;
            this.goal = Math.floor(Math.random() * 101 + 19);
            this.resetVals(this.row1);
            this.resetVals(this.row2);
        },
        resetVals: function(arr) {
            for (let i = 0; i < arr.length; i++) {
                arr[i].val = Math.floor(Math.random() * 11 + 1);
            }
        },
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
.top {
    -moz-box-shadow: inset 0 -6px 8px -4px #000000;
    -webkit-box-shadow: inset 0 -6px 8px -4pxx #000000;
    box-shadow: inset 0 -6px 8px -4px #000000;
}
.bottom {
    -moz-box-shadow: inset 0 8px 6px -6px #000000;
    -webkit-box-shadow: inset 0 8px 6px -6px #000000;
    box-shadow: inset 0 8px 6px -6px #000000;
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
