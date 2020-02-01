<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>

    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/jokes">Jokes</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
}
</script>

<style scoped>
.header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1em;
  padding: 1em 2em;
  border-bottom: 1px dotted #ccc;
}

header .title{
  color: #526488;
  font-size: 2.4rem;
}

header ul{
  display: flex;
  list-style: none;
}

ul li a {
  display: inline-block;
  text-decoration: none;
  margin: .5em 1em;
  padding: 7px 15px;
  color: #fff;
  background: #333;
  border-radius: 3px;
}

</style>