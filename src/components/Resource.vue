<template>
    <div id="wrapper">
        <img
            v-on:click="$emit('add-to-current', resourceVal)"
            :src="require(`@/assets/${filename}`)"
            :alt="altText"
        />
    </div>
</template>

<script>
export default {
    props: {
        filename: String,
        altText: String,
        resourceVal: Number,
    },
};
</script>

<style scoped>
img {
    box-shadow: 5px 10px 18px #888888;
}
img:active {
    box-shadow: none;
}
img:hover {
    cursor: pointer;
}
</style>
