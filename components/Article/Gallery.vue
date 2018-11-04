<template>
  <div
    ref="gallery"
    class="gallery">
    <div
      v-for="(imgItem, index2) in imgArray"
      :key="index2"
      class="gallery__frame">
      <img 
        :src="imgItem.imgSrc"
        class="gallery__image">
      <span class="gallery__frame__plus">
        <svg 
          width="17" 
          height="17" 
          viewBox="0 0 17 17" 
          fill="none" 
          xmlns="http://www.w3.org/2000/svg">
          <path 
            d="M16.0144 7.51453H9.48557V0.985814C9.48557 0.442141 9.04436 0 8.5 0C7.95564 0 7.51443 0.442141 7.51443 0.985581V7.51453H0.985568C0.441438 7.51453 0 7.95668 0 8.50012C0 9.04542 0.441438 9.4857 0.985568 9.4857H7.51443V16.0144C7.51443 16.5602 7.95564 17 8.5 17C9.04436 17 9.48557 16.5595 9.48557 16.0144V9.4857H16.0144C16.559 9.4857 17 9.04518 17 8.50012C17 7.95668 16.5588 7.51453 16.0144 7.51453Z" 
            fill="#5A5AFF"/>
        </svg>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imgArray: {
      type: Array,
      default: function() {
        return {}
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
.gallery {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  overflow: hidden;

  &__image {
    width: 100%;
    height: auto;
  }

  &__frame {
    position: relative;
    width: 25%;
    height: 50%;
    line-height: 0;

    &__plus {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      display: flex;
      justify-content: center;
      align-items: center;
      width: 53px;
      height: 53px;
      opacity: 0;
      background: #ffffff;
      border-radius: 3px;
      transition: 0.5s all;
    }

    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      display: block;
      width: 100%;
      height: 100%;
      opacity: 0;
      transition: 1s all;

      background: #5a5affe4;
    }

    &:hover {
      & > .gallery__frame__plus {
        opacity: 1;
        border-radius: 50%;
        transition: 1s 0.2s all;
      }

      &::before {
        opacity: 1;
        transition: 1s 0.2s all;
      }
    }
  }
}
</style>
