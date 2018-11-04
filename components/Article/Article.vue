<template>
  <div class="article">
    <h2 class="container article__title">{{ articleInfo.title }}</h2>
    <div 
      v-for="(contentItem, index) in articleInfo.content"
      :key="index">
      <p 
        v-if="contentItem.type=='text'"
        class="container article__text">
        {{ contentItem.text }}
      </p>
      <p
        v-if="contentItem.type=='quote'"
        class="container article__quote">
        {{ contentItem.text }}
      </p>
      <img
        v-if="contentItem.type=='image'"
        :src="contentItem.imgSrc"
        class="article__image">
      <TextArray
        v-if="contentItem.type=='textArray'"
        :text-array="contentItem.text"
        class="container"/>
      <!-- <div
        v-if="contentItem.type=='textArray'">
        <p class="container">
          <span 
            v-for="(textItem, index2) in contentItem.text"
            :key="index2">
            {{ textItem.text }}
          </span>
        </p>
      </div> -->
      <Gallery 
        v-if="contentItem.type=='imgArray'"
        :img-array="contentItem.imgArray" />
    </div>
  </div>
</template>

<script>
import Gallery from './Gallery.vue'
import TextArray from './TextArray.vue'

export default {
  components: {
    Gallery,
    TextArray
  },
  props: {
    articleInfo: {
      type: Object,
      default: function() {
        return {
          title: 'TitleError'
        }
      }
    }
  },
  mounted() {
    if (this.$refs.gallery && this.$refs.gallery[0]) {
      var gallery = this.$refs.gallery[0]
      this.resize(gallery)
      window.addEventListener('resize', () => this.resize(gallery))
    }
  },
  methods: {
    resize(gallery) {
      gallery.style.height = gallery.clientWidth / 2 + 'px'
    }
  }
}
</script>

<style lang="scss" scoped>
.article {
  margin-bottom: 50px;

  &__image {
    margin-bottom: 40px;
    width: 100%;
    height: auto;
  }

  &__text {
    margin-bottom: 40px;
    font-family: Helvetica-Roman;
  }

  &__quote {
    font-family: Lora-Italic;
    font-size: 20px;
    margin-bottom: 40px;
    text-align: center;
    padding: 0 95px;
  }

  &__title {
    margin-bottom: 30px;
  }
  &:nth-child(1) > &__title {
    font-size: 36px;
    line-height: 36px;
  }
  &:nth-child(2) > &__title {
    font-size: 30px;
    line-height: 30px;
  }
  &:nth-child(3) > &__title {
    font-size: 24px;
    line-height: 24px;
  }
}
</style>
