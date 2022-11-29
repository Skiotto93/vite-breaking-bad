<script>
import AppCard from './AppCard.vue'
import axios from 'axios'
import { store } from '../store.js'

export default {
    name: 'AppMain',
    components: {
        AppCard,
        store,
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
    computed() {

    }
}
</script>

<template>
    <form>
        <select class="choice" name="category" >
            <option selected>Select Category</option>
            <option value="Breaking Bad">Breaking Bad</option>
            <option value="Better Call Saul">Better Call Saul</option>
        </select>
    </form>
    <section class="container">
        <div class="count">Found {{ characters.length }} characters</div>
        <div class="d-flex">
            <AppCard v-for="character in characters" :info="character"/>
        </div>
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
    
}
.d-flex {
    display: flex;
    flex-wrap: wrap;
}
.count {
    width: 100%;
    background-color: #212529;
    padding: 20px;
    color: #fff;
    margin-bottom: 15px;
}
</style>