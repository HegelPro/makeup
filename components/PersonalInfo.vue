<template>
  <div class="personal">
    <img 
      class="personal__image" 
      src="../assets/bitmap.png">
    <div class="personal__text">
      <div class="personal__name">
        {{ personalInfo.name }}
      </div>
      <div class="personal__blog">
        <span class="personal__line"/>
        Blog
      </div>
    </div>
  </div>
</template>

<script>
import personalInfo from '../static/personal-info.json'

export default {
  data() {
    return {
      personalInfo
    }
  }
}
</script>

<style lang="scss" scoped>
$font-size-big: 18px;
$line-color: #ffffff;
$font-color: #ffffff;

.personal {
  display: flex;

  &__image {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    margin-right: 27px;
  }

  &__text {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  &__name {
    font-size: $font-size-big;
    color: $font-color;
  }

  &__line {
    display: block;
    width: 19px;
    height: 3px;
    background: $line-color;
    margin-right: 8px;
  }

  &__blog {
    display: flex;
    align-items: center;
    color: $font-color;
  }
}
</style>
