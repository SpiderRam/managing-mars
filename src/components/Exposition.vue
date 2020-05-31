<template>
    <div class="hello">
        <h1>Managing Mars</h1>
        <p>
            Okay, yeah, look, this is a weak spin on the greatest tabletop game
            thus far conceived,
            <a
                href="https://boardgamegeek.com/boardgame/167791/terraforming-mars"
                target="_blank"
                >Terraforming Mars</a
            >.
        </p>
        <p>
            If you haven't played the real game, get some friends together and
            try it, you will not be sorry.
        </p>
        <h4>Rules:</h4>
        <ul>
            <li>You have a goal to reach, but not exceed.</li>
            <li>
                Click on the resources that can help you in that endeavor, each
                has a numerical value.
            </li>
            <li>
                You have to figure out what each resource is worth, every game
                the value is different.
            </li>
            <li>Not all games are winnable.</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String,
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
    font-family: 'Russo One', sans-serif;
}

h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
    width: 80vw;
    min-width: 375px;
    margin: 0 auto;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
