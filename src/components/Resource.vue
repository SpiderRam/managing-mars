<template>
    <div id="wrapper">
        <img :src="require(`@/assets/${filename}`)" :alt="{ altText }" />
    </div>
</template>

<script>
export default {
    props: {
        filename: String,
        altText: String,
    },
};
</script>

<style scoped></style>
