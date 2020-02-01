<template>
  <div class="joke">
    <nuxt-link to="/jokes" style="fontSize:12px;">back </nuxt-link>
    <h2>{{ joke }}</h2>
    <hr>
    <small>{{$route.params.id}}</small>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return{
      joke: ""
    }
  },
  async created(){
    const config = {
      headers: {
        'Accept' : 'application/json'
      }
    }

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);

      this.joke = res.data.joke;
      console.log(res.data);
    } catch (err) {
      console.log(err);
    }
  }
}
</script>

<style scoped>
.joke{
  margin: 1em 0;
  padding: 1em;
  border: 1px dotted #ccc;
}
</style>