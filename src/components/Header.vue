<template>
  <div class="header">
      <img src="@/assets/logo.png" alt="Logo Spotify">
      <div class="choose-genre">
        <label>Choose your genre</label>
        <select>
            <option value=''>All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
      </div>
  </div>
</template>

<script>

export default {
    name: 'Header',
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