<template>
  <nuxt-link :to="`jokes/${id}`">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: ['joke', 'id']
}
</script>

<style scoped>
.joke{
  background: #fff;
  padding: 1rem;
  margin: 1rem 0;
  border: 1px dotted #ccc;
}
.joke:hover{
  background: rgb(245, 245, 245);
}
</style>