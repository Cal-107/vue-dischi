<template>
  <section class="main-section">
       <div class="container" v-if="albumList.length !== 0">
            <div class="list-container"
                 v-for="(album, i) in albumList" :key="`album-${i}`"
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
import axios from 'axios';
import Card from '@/components/Card.vue';
import Loader from '@/components/Loader.vue';

export default {
    name: 'Main',
    components: {
        Card,
        Loader,
    },
    data() {
        return {
            albumList: [],
        };
    },

    created() {
        this.getAlbumList();
    },

    methods: {
        getAlbumList() {
            axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(response => {
                this.albumList = response.data.response;
            })
            .catch(error => console.log(error));
        },
    },
}
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.main-section {
    background-color: $bg-1;
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