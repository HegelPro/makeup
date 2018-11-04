<template>
  <main>
    <div class="main__header">
      <div class="main__row main__row">
        <a
          href="#"
          class="main__link">
          NewTrends
        </a>
        <p>12.12. 2017</p>
      </div>
      <div class="main__row main__row--column">
        <strong class="main__accent">I Create Website Design, that Make Sense<span>.</span></strong>
        <p class="quote">{{ quotes[0] }}</p>
      </div>
      <div class="main__row main__row--center">
        <Mouse />
      </div>
    </div>
    <ArticleList />
    <Resume class="container" />
  </main>
</template>

<script>
import quotes from '../static/quotes.json'
import Mouse from './Mouse.vue'
import ArticleList from './Article/Article-list.vue'
import Resume from './Resume.vue'

export default {
  components: {
    Mouse,
    ArticleList,
    Resume
  },
  data() {
    return {
      quotes
    }
  }
}
</script>

<style lang="scss" scoped>
$font-size-big: 18px;
$font-size-title: 46px;

.main {
  &__accent {
    font-size: $font-size-title;
    line-height: 60px;
    margin-bottom: 30px;
  }

  &__header {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 62px 75px 62px 75px;
    min-height: 100%;
    margin-bottom: 77px;
  }

  &__link {
    color: #5a5aff;
    text-decoration: none;

    &:hover {
      transform: scale(1.1);
      transition: transform 0.6s;
    }
  }

  &__row {
    display: flex;
    width: 100%;
    justify-content: space-between;
    &--column {
      flex-direction: column;
    }
    &--center {
      justify-content: center;
    }
  }
}

.quote {
  font-family: Lora-Italic;
  font-size: $font-size-big;
}
</style>
