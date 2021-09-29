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
.song{
    text-align: center;
    h5{
    color: $titleColor;
    padding: 1rem;
    font-weight: 700;
    font-size: 1rem;
    }
    p{
        color: $pColor;
        margin: 0;
        font-weight: 500;
        font-size: 0.8rem;
    }
}


</style>