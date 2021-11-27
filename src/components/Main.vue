<template>
  <section class="main-section">
       <div class="container" v-if="cardList.length !== 0">
            <div class="list-container"
                 v-for="(album, i) in cardList" :key="`album-${i}`"
            >
                <Card 
                      :image="album.poster"
                      :title="album.title"
                      :subTitle="album.author"
                      :text="album.year"
                      :text2="album.genre"
                />
            </div>
       </div>
       <Loader v-else /> 
  </section>
</template>

<script>
import Card from '@/components/Card.vue';
import Loader from '@/components/Loader.vue';

export default {
    name: 'Main',
    components: {
        Card,
        Loader,
    },
    props: {
        cardList: Array,
    }
}
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.main-section {
    background-color: $bg-1;
    height: 100%;
    .container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        padding: 6rem 3rem;
        .list-container {
            width: calc(100% / 8);
            padding: 1rem;
        }
    }
}
</style>