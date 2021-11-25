<template>
  <div class="header">
      <img src="@/assets/logo.png" alt="Logo Spotify">
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
    background-color: $bg-1;
}

img {
    width: 60px;
    margin: .5rem;
}
</style>