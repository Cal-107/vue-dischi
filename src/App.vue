<template>
  <div id="app">
    <Header @toSetValue="setValue" :genreList="genreList"/>

    <Main :cardList="filteredAlbum" />
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
        return {
            albumList: [],
            valueSelect: '',
            genreList: [],
        };
    },
    computed: {
      filteredAlbum() {
        if (this.valueSelect === '') {
          return this.albumList
        }

        return this.albumList.filter(el => {
          return el.genre.includes(this.valueSelect)
        })
      }
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

                this.albumList.forEach(el => {
                  if (!this.genreList.includes(el.genre)) {
                    this.genreList.push(el.genre)
                  } 
                })
            })
            .catch(error => console.log(error));
        },
        setValue(value) {
          this.valueSelect = value;
        }
    },
}
</script>

<style lang="scss">
@import '@/styles/variables';
@import '@/styles/globals';
</style>
