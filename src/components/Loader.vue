<template>
  <div class="loader">
      <div class="text">
          Your music is coming         
      </div>
      <div class="img-box">
          <img src="@/assets/logo.png" alt="">
      </div>

      
      
  </div>
</template>

<script>
export default {
    name: 'Loader',
}
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.loader{
    height: 100%;
    display: flex;
    flex-direction: column;
    text-align: center;
    justify-content: center;
    .text {
        font-size: 4rem;
    }
    .img-box {
        padding: 2rem;
        img {
            width: 100px
        }
        animation: rotate 1s infinite alternate;
    }

    @keyframes rotate {
        from {
            
            transform: rotate(0deg);
        }
        to {
            transform: rotate(359deg);
        }
    }
}
</style>