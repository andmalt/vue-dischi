<template>
  <main class="container-fluid px-5 py-3">
    <div class="row g-5">
      <div v-for="(song , index) in songs" :key="index" class="col-lg-2 col-md-4 col-12 box-song mx-3">
        <BoxSong :song="song"/>
      </div>
    </div>
  </main>
</template>

<script>
import BoxSong from './BoxSong.vue';
import axios from 'axios';

export default {
  name: 'Main',
  components:{
    BoxSong,
  },
  data:function(){
    return{
      songs:[],
    }
  },
  created:function(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      this.songs = res.data.response.slice();
      console.log(this.songs);
    });
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/general.scss';
@import '../style/variables.scss';

main{
  background-color: $backgroundColor;
}
.box-song{
  background-color: $boxColor;
}
</style>
