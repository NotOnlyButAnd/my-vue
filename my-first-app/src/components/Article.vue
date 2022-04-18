<template>
  <div class="article" v-bind:class="{nonPublicated: !isPublicated}">
    <h1 v-if="id">
      ID: {{ id }}        
    </h1>
    <h1 v-if="title">
      {{ title }}        
    </h1>
    <p v-if="body">
      {{ body }}        
    </p> 
  </div>
</template>

<script>

export default {
  name: 'ArticleItem',
  props: {
    msg: String,
    title: String,
    body: String,
    id: Number,
    isPublicated: Boolean
  }
}
</script>

<style scoped>
.article{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
h1{
    color: #2c503a;
    font-size: 1em;
}
.nonPublicated{
  background-color: #995252;
}
</style>