<template>
  <div class="article-item">
    <h3>{{article.title}}</h3>
    <p>
      {{article.description}}
      <button @click="showArticle = true">
        more
        <ArticleItemPopup v-if="showArticle" label="Article" @close="showArticle = false">
          <h3>{{article.title}}</h3>
          <h4>By: {{article.author}}</h4>
          <img
            class="article-image"
            v-if="article.urlToImage"
            :src="article.urlToImage"
            :alt="article.title"
          />
          <p>{{article.content}}</p>
          <a v-bind:href="article.url" target="_blank">{{article.url}}</a>
        </ArticleItemPopup>
      </button>
    </p>
    <a v-bind:href="article.url" target="_blank">{{article.url}}</a>
  </div>
</template>

<script>
import ArticleItemPopup from "./articleItemPopup";

export default {
  name: "ArticleItem",
  components: {
    ArticleItemPopup
  },
  data() {
    return {
      showArticle: false
    };
  },
  props: ["article"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.article-image {
  height: 200px;
}
</style>
