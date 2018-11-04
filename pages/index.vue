<template>
  <div class="window">
    <Header class="helf-of-screen" />
    <Main class="helf-of-screen helf-of-screen--right" />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Main from '~/components/Main.vue'

export default {
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
$font-size-normal: 16px;
$font-size-big: 18px;

.container {
  padding: 0 75px;
}

.window {
  display: flex;
  flex-wrap: wrap;
}

.helf-of-screen {
  width: 50%;
  height: 100vh;
  overflow-y: auto;
  overflow-x: hidden;
  &--right {
    min-height: 100vh;
  }
}

@media (max-width: 900px) {
  .helf-of-screen {
    width: 100%;
    min-width: 375px;
    overflow: unset;
  }
}

@font-face {
  font-family: Helvetica-Bold;
  src: url('../assets/fonts/HelveticaNeueCyr-Bold.otf');
}

@font-face {
  font-family: Helvetica-Roman;
  src: url('../assets/fonts/HelveticaNeueCyr-Roman.otf');
}

@font-face {
  font-family: Lora-Italic;
  src: url('../assets/fonts/Lora-Italic.ttf');
}
</style>
