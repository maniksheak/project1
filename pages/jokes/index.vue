<template>
    <div> 
        <SearchVue v-on:search-text="searchText"></SearchVue>
        <jokeVue v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" ></jokeVue>
        </div>
</template>

<script>
import axios from 'axios';
import jokeVue from '../../components/joke.vue'; 
import SearchVue from '../../components/Search.vue';

export default {
components: {
    jokeVue,
    SearchVue
},

 data() {
        return {
            jokes: []
        }
    },
    async created() {
        const config = {
            headers: {
             'Accept': 'application/json'   
            }
        };

        try {
            const res = await axios.get('https://icanhazdadjoke.com/search', config);

            this.jokes = res.data.results;

        } catch (err) {
            console.log(err);
        }
        
    },
    methods: {
     async searchText(text) {
        const config = {
            headers: {
             'Accept': 'application/json'   
            }
        };

        try {
            const res = await axios.get(`https://icanhazdadjoke.com/search?term= ${text}`, config);

            this.jokes = res.data.results;

        } catch (err) {
            console.log(err);
        }   
      },
    },

   head() {
        return {
            title: 'Manik Makes',
            meta: [
                {
                    hid: 'Description',
                    name: 'Description',
                    content: 'Best Place for corny manik jokes'
                }
            ]
        };
    },
}
</script>

<style>
   /* .jokes {
    padding: 1rem;
   } */
</style>