<template>
  <div class="general-card-container">
      <div class="img-box">
          <img :src=" image " alt="title">
      </div>
      <div class="box">
          <h1 class="pb title">
              {{ title }}
          </h1>
          <div class="pb-2 subTitle">
              {{ subTitle }}                        
          </div>
          <div class="pb-2 text">
              {{ text }}                        
          </div>
          <div class="pb-2 text2">
              {{ text2 }}                        
          </div>                 
      </div> 
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        image: String,
        title: String,
        subTitle: String,
        text: String,
        text2: String
    }

}
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.general-card-container {
                background-color: $bg-2;
                height: 100%;
                display: flex;
                flex-direction: column;
                .img-box {
                    width: 100%;
                    height: 300px;
                    
                    img {
                        padding: 1rem;
                        object-fit: contain;
                        object-position: top;
                        width: 100%;
                        height: 100%;
                    }
                }
                .box {
                    height: 50%;
                    text-align: center;
                    .pb {
                        padding-bottom: 1rem;
                    }
                    .pb-2 {
                        padding-bottom: .5rem;
                    }
                    .title {
                        text-transform: uppercase;
                        font-weight: 500;
                        padding-right: 1.5rem;
                        padding-left: 1.5rem;
                    }
                    .subTitle,
                    .text {
                        color: $text-color-2;
                    }
                    .text2 {
                        font-size: 1.3rem;
                    }
                }
            }
</style>