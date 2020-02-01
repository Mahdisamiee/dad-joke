<template>
  <div>
    <SearchJokes v-on:search-text="searchText"/>
    <joke v-for="joke in jokes" :key="joke.id" :joke="joke.joke" :id="joke.id" />
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/jokes.vue";
import SearchJokes from "../../components/SearchJokes.vue";


export default {
  components: {
    Joke,
    SearchJokes
  },
  data() {
    return{
      jokes : []
    }
  },
  methods:{
    async searchText(text){
      const config = {
        headers: {
          'Accept' : 'application/json'
        }
      }

      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`,config);

        this.jokes = res.data.results;
      } catch (err) {
        console.log(err.message);
      }
    }
  },
  async created() {
    const config = {
      headers: {
        'Accept' : 'application/json'
      }
    }

    try {
      const res = await axios.get("https://icanhazdadjoke.com/search",config);

      this.jokes = res.data.results;
    } catch (err) {
      console.log(err.message);
    }
  },
  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "best place for corny jokes"
        }
      ]
    }
  }
}
</script>

<style>

</style>