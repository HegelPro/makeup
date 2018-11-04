<template>
  <header class="header header--bg">
    <div class="header__row">
      <PersonalInfo />
      <Menu />
    </div>
    <div class="header__row header__row--bottom">
      <a 
        href="#" 
        class="header__link">
        <svg 
          width="13" 
          height="11" 
          viewBox="0 0 13 11" 
          fill="none"
          class="header__link__arrow"
          xmlns="http://www.w3.org/2000/svg">
          <path 
            d="M11.3817 4.65028L4.03815 4.65398L6.35208 2.36961C6.46539 2.25808 6.52755 2.107 6.52755 1.94843C6.52755 1.78986 6.46539 1.63983 6.35208 1.52804L5.99203 1.17319C5.87881 1.06167 5.72794 1 5.56706 1C5.40608 1 5.25512 1.06123 5.1419 1.17275L1.17538 5.07966C1.06171 5.19163 0.999555 5.34077 1 5.49943C0.999555 5.65897 1.06171 5.8082 1.17538 5.91999L5.1419 9.82725C5.25512 9.93869 5.40599 10 5.56706 10C5.72794 10 5.87881 9.9386 5.99203 9.82725L6.35208 9.4724C6.46539 9.36105 6.52755 9.21235 6.52755 9.05378C6.52755 8.89529 6.46539 8.75443 6.35208 8.64299L4.01203 6.34584H11.3899C11.7214 6.34584 12 6.06438 12 5.73799V5.23611C12 4.90972 11.7132 4.65028 11.3817 4.65028Z" 
            fill="#5A5AFF" 
            stroke="#5A5AFF"/>
        </svg>
        Go to my website
      </a>
      <Social />
    </div>
  </header>  
</template>

<script>
import PersonalInfo from './PersonalInfo.vue'
import Menu from './Menu.vue'
import Social from './Social.vue'

export default {
  components: {
    PersonalInfo,
    Menu,
    Social
  }
}
</script>

<style lang="scss" scoped>
$font-color: #ffffff;

.header {
  padding: 38px 75px 65px 75px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;

  &__link {
    font-size: 16px;
    color: $font-color;
    text-decoration: none;
    padding: 5px 10px;
    border-radius: 10px;
    transition: all 0.4s;

    &__arrow {
      margin-right: 10px;
    }

    &:hover {
      background: #5a5aff;
      transform: scale(1.1);

      & > .header__link__arrow > path {
        transition: fill 0.7s;
        fill: #ffffff;
        transition: stroke 0.5s;
        stroke: #ffffff;
      }
    }
  }

  &__row {
    display: flex;
    justify-content: space-between;

    &--bottom {
      align-items: flex-end;
    }
  }

  &--bg {
    background: url('../assets/backgroud-image.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: 50%;
    background-position-y: 50%;
  }
}
</style>
