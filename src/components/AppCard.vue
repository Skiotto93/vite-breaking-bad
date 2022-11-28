<script>
export default {
    name: 'AppCard',
    props: {
        info: Object,
    },
}
</script>

<template>
    <div class="card">
        <img :src="info.img" alt="photo">
        <h3 class="character">{{ info.name }}</h3>
        <div class="series">{{ info.category }}</div>
        <div class="status">{{ info.status }}</div>
    </div>
</template>

<style lang="scss" scoped>
.card {
        width: calc(100% / 5 - 20px);
        margin: 10px;
        padding: 20px;
        text-align: center;
        background-color: #2e3a46;
        img {
            width: 100%;
        }
        h3 {
            color: #fff;
            margin: 25px 0;
        }
        .series, .status {
            color: #4d5d6c;
            margin-bottom: 5px;
        }
        .character {
            text-transform: uppercase;
        }
    }
</style>