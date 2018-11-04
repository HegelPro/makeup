<template>
  <div class="toggle-menu">
    <button 
      ref="toggle"
      class="toggle">
      <span class="toggle__line" />
    </button>
    <nav class="menu">
      <ul class="menu__list">
        <li><a 
          href="#"
          class="menu__item">Home</a></li>
        <li><a
          href="#"
          class="menu__item">About</a></li>
        <li><a
          href="#"
          class="menu__item">Contact</a></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$refs.toggle.addEventListener('click', () =>
      this.$refs.toggle.classList.toggle('on')
    )
  }
}
</script>


<style lang="scss">
.toggle-menu {
  position: relative;
  align-self: center;
}
.menu {
  position: absolute;
  top: 24px + 15px + 5px;
  right: -8px;
  color: #999999;
  width: 200px;
  padding: 10px;
  margin: auto;
  text-align: center;
  border-radius: 4px;
  background: white;
  box-shadow: 0 1px 8px #0000000d;

  opacity: 0;
  visibility: hidden;
  transition: opacity 0.4s;

  &__list {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  &__item {
    display: block;
    padding: 5px;
    color: #888;
    text-decoration: none;
    transition: all 0.2s;

    &:hover,
    &:focus {
      background: #5a5aff;
      color: #fff;
    }
  }

  &:after {
    position: absolute;
    top: -15px;
    right: 5px;
    content: '';
    display: block;
    border-left: 15px solid transparent;
    border-right: 15px solid transparent;
    border-bottom: 20px solid white;
  }
}

.toggle {
  display: block;
  width: 24px;
  height: 24px;
  background: none;
  padding: 0;
  border: none;
  transition: transform 0.7s;

  &__line {
    position: relative;
    display: block;
    width: 100%;
    height: 3px;
    background-color: #ffffff;
    transition: all 0.3s;
    backface-visibility: hidden;
    border-radius: 2px;

    &:after,
    &:before {
      content: '';
      display: block;
      width: 100%;
      height: 3px;
      background-color: #ffffff;
      border-radius: 2px;
      position: absolute;
      left: 0;
      top: -9px;
      transition: all 0.3s;
    }
    &:after {
      top: 9px;
    }
  }
  &.on {
    & + .menu {
      opacity: 1;
      visibility: visible;
    }

    & > .toggle__line {
      background-color: transparent;

      &:before {
        transform: rotate(45deg) translate(5px, 5px);
      }

      &:after {
        transform: rotate(-45deg) translate(7px, -8px);
      }
    }
  }

  &:hover {
    transform: scale(1.2);
    transition: transform 0.7s;
  }
}
</style>
