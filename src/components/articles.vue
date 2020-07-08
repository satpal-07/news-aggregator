<template>
  <div>
    <div class="articles" v-bind:key="article.title" v-for="article in articles">
      <ArticleItem v-bind:article="article" />
    </div>
  </div>
</template>

<script>
import ArticleItem from './articleItem.vue';
export default {
  name: "Articles",
  components: {
    ArticleItem
  },
  props: ["articles"]
}
</script>

<style scoped>
.articles {
  background-color: rgb(255, 255, 255);
  padding: 20px 100px;
  margin: 20px 100px;
}
</style>