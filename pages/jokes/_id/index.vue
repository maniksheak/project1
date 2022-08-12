<template>
    <div> 
        <nuxt-link to="/jokes">Back to jokes</nuxt-link>
        <h2> {{ joke }}</h2>
        <hr>
        <small> Joke ID: {{ $route.params.id}}</small>
         </div>
</template>

<script>
import axios  from 'axios';

export default {
  data() {
        return {
            joke: []
        }
    },
    async created() {
        const config = {
            headers: {
             'Accept': 'application/json'   
            }
        };

        try {
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.params.id}`, config);

            this.joke = res.data.joke;
            console.log(this.joke);

        } catch (err) {
            console.log(err);
        }
        
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

</style>
