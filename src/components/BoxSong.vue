<template>
  <div class="song ">
      <img class="img-fluid" :src="song.poster" :alt="song.title">
      <h5>{{ song.title }}</h5>
      <p>{{ song.author }}</p>
      <p>{{ song.year }}</p>
  </div>
</template>

<script>
export default {
    name:'boxSong',
    props:{
        song:Object,
    }
}
</script>

<style lang="scss">
@import '../style/general.scss';
@import '../style/variables.scss';

</style>