<template>
  <div class="mouse">
    <svg 
      class="mouse__top-part"
      width="11" 
      height="12" 
      viewBox="0 0 11 12" 
      fill="none" 
      xmlns="http://www.w3.org/2000/svg">
      <path 
        d="M4.65028 1.56211L4.65398 8.23805L2.36961 6.13447C2.25808 6.03146 2.107 5.97496 1.94843 5.97496C1.78986 5.97496 1.63983 6.03146 1.52804 6.13447L1.17319 6.46179C1.06167 6.56471 1 6.70187 1 6.84813C1 6.99447 1.06123 7.13171 1.17275 7.23463L5.07966 10.8406C5.19163 10.9439 5.34077 11.0004 5.49943 11C5.65897 11.0004 5.8082 10.9439 5.91999 10.8406L9.82725 7.23463C9.93869 7.13171 10 6.99455 10 6.84813C10 6.70187 9.9386 6.56471 9.82725 6.46179L9.4724 6.13447C9.36105 6.03146 9.21235 5.97496 9.05378 5.97496C8.89529 5.97496 8.75443 6.03146 8.64299 6.13447L6.34584 8.26179L6.34584 1.55463C6.34584 1.25325 6.06438 1 5.73799 1H5.23611C4.90972 1 4.65028 1.26073 4.65028 1.56211Z" 
        fill="#5A5AFF" 
        stroke="#5A5AFF"/>
    </svg>
    <svg 
      width="24" 
      height="35" 
      viewBox="0 0 24 35" 
      fill="none" 
      xmlns="http://www.w3.org/2000/svg">
      <rect 
        x="1.5" 
        y="1.49997" 
        width="21" 
        height="32" 
        rx="10.5" 
        stroke="#5A5AFF" 
        stroke-width="3"/>
      <rect 
        x="10.5769" 
        y="7.5769" 
        width="2.84615" 
        height="8.17949" 
        rx="1.42308" 
        fill="#5A5AFF" 
        stroke="#5A5AFF"/>
    </svg>
  </div>
</template>

<style lang="scss" scoped>
.mouse {
  display: flex;
  flex-direction: column;
  align-items: center;

  &:hover {
    & > .mouse__top-part {
      animation-name: mouse-move;
      animation-duration: 1s;
      animation-fill-mode: forwards;
      animation-iteration-count: infinite;
    }
  }
  &__top-part {
    margin-bottom: 20px;
  }
}
@keyframes mouse-move {
  0% {
    margin-bottom: 20px;
    margin-top: 0px;
  }
  100% {
    margin-top: 15px;
    margin-bottom: 5px;
  }
}
</style>
