<template>
  <div class="header">
      <img src="@/assets/logo.png" alt="Logo Spotify">
      <div class="choose-genre">
        <label>Choose your genre</label>
        <select v-model="genreValue" 
                @change="$emit('toSetValue', genreValue)"
        >
            <option value=''>All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
      </div>
  </div>
</template>

<script>

export default {
    name: 'Header',
    data() {
        return {
            genreValue: '',
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.header {
    background-color: $bg-2;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: .5rem 1rem;
    text-transform: uppercase;
    .choose-genre {
        display: flex;
        align-items: center;
        label {
            margin-right: 1rem;
        }
        select {
            color: $text-color-1;
            background-color: #aaa;
            padding: .4rem;
            border: none;
            border-radius: 30px;
            option {
                border: none;
                background-color: #aaa;
                border-radius: 20px;
            }
        }
    }
}

img {
    width: 60px;
}
</style>