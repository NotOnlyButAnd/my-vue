<template>
  <div id="articleList">
        <h1> {{ msg }} </h1> 

        <!-- Добавление статей - кнопка и переход на новую страницу -->
        <button name="add_article">
            Добавить статью
        </button> 

        <ul v-if="articles.length">
            <Article
                v-for="article in articles"
                v-bind:key="article.id"
                v-bind:id="article.id"
                v-bind:title="article.title"
                v-bind:body="article.body"
                v-bind:isPublicated="article.isPublicated"
                v-bind:author="article.author"
            >
            </Article>
        </ul>
        <p v-else>
            No articles in list
        </p>
        <ArticleForm title="New title" body="" author="" isPublicated=""
        v-on:add-article="addArticle" />
  </div>
</template>

<script>

import Article from './Article.vue'
import ArticleForm from './ArticleForm.vue'


export default {
  name: 'ArticleList',
  props: {
    msg: String
  },
  components:{
      Article,
    ArticleForm
  },
  methods:{
      addArticle: function(article){
          let newArticle = {
              id: this.articles.length+1,
              ...article
          }
          this.articles.push(newArticle);
          console.log(article.title);
      }
  },
  data() {
      return{
          articles: [
              {
                  id: 1,
                  title: 'TITLE 1',
                  body: 'Body 1 - Learn vue',
                  isPublicated: true,
                  author: 'Bob Marley'
              },
              {
                  id: 2,
                  title: 'TITLE 2',
                  body: 'Body 2 - Learn about single-file components',
                  isPublicated: false,
                  author: 'Mark Twen'
              },
              {
                  id: 3,
                  title: 'TITLE 3',
                  body: 'Body 3 - Fall in love',
                  isPublicated: true,
                  author: 'Elisabeth Tetcher'
              }
          ]
      }
  }

}
</script>

<style>
#articleList {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 40px;
}
</style>