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
            This styling is also basically a rip off of the Vue boilerplate code
            created by the CLI.
        </p>
        <p>
            And furthermore, this is a recycled homework assignment from my
            coding bootcamp. Is there anything worth seeing here?
        </p>
        <p>
            I don't know, but it was fun. And the game is stupid but you could
            be wasting time far less productively on the interwebs, so enjoy!
        </p>
        <p>
            But seriously, if you haven't played the real game, get some friends
            together and play it, you will not be sorry. I recommend all of the
            expansions.
        </p>
        <p>
            Well, except Turmoil, but that's because I got it right before COVID
            hit and I haven't had a chance to play a full game yet.
        </p>
        <p>Microbes are far more beneficial in the game....</p>
        <p>Rules:</p>
        <ul>
            <li>You have a goal to reach, but not exceed.</li>
            <li>
                Click on the resources that can help you in that endeavor, each
                has a numerical value.
            </li>
            <li>Told you it was stupid.</li>
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
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}
</style>
