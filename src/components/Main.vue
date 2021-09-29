<template>
  <main class="container-fluid px-5 py-3">
    <div class="row g-3">
      <div class="col-lg-2 col-md-4 col-12 box-song">
        <BoxSong :songs="songs" />
        <h1>prova</h1>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Saepe fugiat minus, cum corporis nemo sint voluptatibus modi tempore laudantium, itaque quod? Optio repudiandae consectetur perferendis accusamus molestiae nihil totam eligendi?</p>
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
      let result = res.data.response
      this.songs.push(result);
      console.log(result);
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
