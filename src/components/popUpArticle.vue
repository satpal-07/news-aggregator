<template>
  <div class="pop-up-article">
    <h3>{{article.title}}</h3>
    <h4>By: {{article.author}}</h4>
    <img v-bind:src="article.urlToImage" v-bind:alt="article.title" width="500" height="600">
    <p>{{article.content}}</p>
    <a  v-bind:href="article.url" target="_blank">{{article.url}}</a>
    <a target="_blank">close</a>
  </div>
</template>

<script>
export default {
  name: "PopUpArticle",
  props: ["article"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
