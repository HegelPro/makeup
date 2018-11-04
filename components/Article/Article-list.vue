<template>
  <div class="article-list">
    <Article
      v-for="(article, index) in articles"
      :key="index"
      :articleInfo="article" />
  </div>
</template>

<script>
import articles from '../../static/articles.json'
import Article from './Article.vue'

export default {
  components: {
    Article
  },
  data() {
    return {
      articles
    }
  }
}
</script>

<style lang="scss">
$font-size-title: 36px;

.article-list {
}
</style>
