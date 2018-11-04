<template>
  <div class="resume">
    <div class="resume__row resume__card">
      <img 
        class="resume__image" 
        src="../assets/bitmap.png">
      <div class="resume__text">
        <div class="resume__text__title">
          {{ personalInfo.name }}
        </div>
        <div class="resume__text__info">
          {{ personalInfo.aboutPerson }}
        </div>
      </div>
    </div>
    <div class="resume__row">
      <div class="resume__sign">MORE FROM AUTHOR</div>
      <div class="resume__line" />
      <div class="resume__btn-container">
        <button class="resume__btn">
          <svg 
            width="7" 
            height="12" 
            viewBox="0 0 7 12" 
            fill="none" 
            xmlns="http://www.w3.org/2000/svg">
            <path 
              d="M0.251851 5.40594L5.53201 0.246289C5.8679 -0.0820961 6.41247 -0.0820961 6.74819 0.246289C7.08394 0.574383 7.08394 1.10652 6.74819 1.43459L2.07606 6.00009L6.74805 10.5654C7.0838 10.8937 7.0838 11.4257 6.74805 11.7538C6.41231 12.0821 5.86776 12.0821 5.53188 11.7538L0.251715 6.5941C0.0838413 6.42998 0 6.2151 0 6.00011C0 5.78502 0.0840044 5.56998 0.251851 5.40594Z" 
              fill="black"/>
          </svg>
          OLDER
        </button>
        <button class="resume__btn" >
          NEWER
          <svg 
            width="7" 
            height="12" 
            viewBox="0 0 7 12" 
            fill="none" 
            xmlns="http://www.w3.org/2000/svg">
            <path 
              d="M6.74815 6.59406L1.46799 11.7537C1.1321 12.0821 0.587529 12.0821 0.25181 11.7537C-0.0839366 11.4256 -0.0839366 10.8935 0.25181 10.5654L4.92394 5.99991L0.251946 1.43457C-0.0838007 1.10635 -0.0838007 0.574263 0.251946 0.24617C0.587692 -0.0820565 1.13224 -0.0820565 1.46812 0.24617L6.74829 5.4059C6.91616 5.57002 7 5.7849 7 5.99989C7 6.21498 6.916 6.43002 6.74815 6.59406Z" 
              fill="black"/>
          </svg>
        </button>
      </div>
    </div>
    <SocialCircul class="resume__btn-social" />
  </div>
</template>

<script>
import personalInfo from '../static/personal-info.json'
import SocialCircul from './Social-circul.vue'

export default {
  components: {
    SocialCircul
  },
  data() {
    return {
      personalInfo
    }
  }
}
</script>

<style lang="scss" scoped>
$color: #05050a;
$btn-color: #5a5aff;

.resume {
  position: relative;
  box-shadow: 0px 0px 17px #00000022;
  padding-top: 66px;
  padding-bottom: 60px;

  &__card {
    margin-bottom: 38px;
  }

  &__image {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    margin-right: 26px;
  }

  &__text {
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    &__title {
      font-size: 18px;
      margin-bottom: 18px;
    }

    &__info {
      font-family: Helvetica-Roman;
      font-size: 14px;
      line-height: 24px;
    }
  }

  &__row {
    display: flex;
    align-items: center;
    width: 100%;
  }

  &__line {
    flex-grow: 2;
    height: 3px;
    background: $color;
  }

  &__btn-container {
    margin-left: 19px;
  }

  &__btn {
    background: transparent;
    border: none;
    font-size: 14px;
    font-family: Helvetica-Bold;
    transition: transform 0.4s;
    color: #2c2c35;

    &:hover {
      transform: scale(1.1);
    }
  }

  &__btn-social {
    position: absolute;
    top: -32px;
    right: 65px;
  }

  &__sign {
    font-size: 14px;
    margin-right: 19px;
  }
}
</style>
