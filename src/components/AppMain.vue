<script>
import AppCard from './AppCard.vue'
import axios from 'axios'

export default {
    name: 'AppMain',
    components: {
        AppCard,
    },
    data() {
        return {
            characters: [],
        }
    },
    created() {
        axios.get("https://www.breakingbadapi.com/api/characters")
        .then((resp) => {
            console.log(resp);
            this.characters = resp.data;
        });
    },
}
</script>

<template>
    <form action="">
        <select class="choice" name="category">
            <option selected>Select Category</option>
            <option value="Breaking Bad">Breaking Bad</option>
            <option value="Better Call Saul">Better Call Saul</option>
        </select>
    </form>
    <section class="container">
        <AppCard v-for="character in characters" :info="character"/>
    </section>
</template>

<style lang="scss" scoped>
.choice {
    padding: 10px;
    border-radius: 5px;
    margin-left: 300px;
    margin-bottom: 30px;
}
.container {
    width: 86.875rem;
    margin: auto;
    background-color: #fff;
    padding: 20px;
    display: flex;
    flex-wrap: wrap;
}

</style>