<template>
  <div id="app" class="p-md-5">
    <Main/>
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main,
  }
}
</script>


<style lang="scss">
@import './style/general.scss';
@import './style/variables.scss';

*{
  font-family: $mainFont;
}
#app{
  background-color: $backgroundColor;
  min-height: 100vh;
}

</style>
