<template>
  <div class="article">
        <li>
            <h1>
                ID: {{ id }}        
            </h1>
            <h1 v-if="title">
                {{ title }}        
            </h1>
            <p v-if="body">
                {{ body }}        
            </p>
        </li>
  </div>
</template>

<script>

export default {
  name: 'ArticleItem',
  props: {
    msg: String,
    title: String,
    body: String,
    id: Number
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
</style>