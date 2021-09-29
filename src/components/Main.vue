<template>
  <main class="container px-5 py-3">
    <div class="row row-cols-lg-6 row-cols-sm-3 row-cols-1 justify-content-center g-4 px-md-5">
      <div v-for="(song , index) in songs" :key="index" class="col box-song p-3 mx-3">
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

.box-song{
  background-color: $boxColor;
}
</style>
