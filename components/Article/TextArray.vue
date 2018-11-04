<template>
  <p class="text-array">
    <template
      v-for="(textItem, index2) in textArray">
      <span
        v-if="textItem.type=='text' | textItem.type=='bold'"
        :key="index2"
        :class="{'text-array__text--bold': textItem.type=='bold', 'text-array__text--normal': textItem.type=='text'}">
        {{ textItem.text }}
      </span>
      <a 
        v-else-if="textItem.type=='link'"
        :key="index2"
        :href="textItem.href"
        class="text-array__text--link">
        {{ textItem.text }}
      </a>
    </template>
  </p>
</template>

<script>
export default {
  props: {
    textArray: {
      type: Array,
      default: function() {
        return []
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.text-array {
  margin-bottom: 40px;

  &__text {
    &--normal {
      font-family: Helvetica-Roman;
    }
    &--bold {
      font-family: Helvetica-Bold;
    }
    &--link {
      color: #5a5aff;
      text-decoration: none;
      padding-bottom: 3px;
      margin-bottom: -3px;
      border-bottom: #5a5aff solid 1px;
    }
  }
}
</style>
