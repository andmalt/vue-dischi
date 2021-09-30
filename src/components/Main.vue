<template>
  <main class="container px-5 py-3">
    <div v-if="booleanResponse == true" class="row px-md-5">
      <!-- selector -->
      <div class="col-12 text-center">
        <SelectBox @choise="myChoises" :song="generes"/>
      </div>
      <!-- songs container -->
      <div class="col-12">
        <div class="row row-cols-lg-6 row-cols-sm-3 row-cols-1 justify-content-center g-4 ">
          <div v-for="(song , index) in songs" :key="index" class="col box-song p-3 mx-3">
            <BoxSong :song="song"/>
          </div>
        </div>
      </div>
    </div>

    <div v-else class="row ">
      <div id="loader-box" class="col-12">
        <Loader/>
      </div>
    </div>

  </main>
</template>

<script>
import BoxSong from './BoxSong.vue';
import Loader from './Loader.vue';
import axios from 'axios';
import SelectBox from './SelectBox.vue';

export default {
  name: 'Main',
  components:{
    BoxSong,
    Loader,
    SelectBox,
  },
  data:function(){
    return{
      songs:[],
      booleanResponse: false,
      myChoises:'',
    }
  },
  methods:{

  },
  computed:{
    // filtered array for genre
    generes:function(){
      const newArray = this.songs.map((element) =>{
      return element.genre;
      });
      // making sure that there aren't duplicates
      const arrayGeneres = newArray.filter((element,index)=>{
        if(newArray.indexOf(element) == index ){
          // console.log(element);
          return element;
        }
      })
      // console.log('arrGen'+ arrayGeneres);
      return arrayGeneres;
    },

  },
  created:function(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(res => {
      this.songs = res.data.response.slice();
      // console.log(this.songs);
      setTimeout(() => {
        this.booleanResponse = true;
      },2500);
      
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
#loader-box{
  min-height: 100vh;
}
</style>
