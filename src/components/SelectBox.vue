<template>
    <form class="d-flex justify-content-center pb-3"  v-on:submit.prevent>
        <label for="genre">Seleziona genere di musica</label>
        <select v-model="options" name="genre" class="ms-3" id="selector">
            <option v-for="element in song" :key="element" >{{ element }}</option>
        </select>  
    </form>
</template>

<script>
export default {
    name:'SelectBox',
    data(){
        return{
            options:'',
        }
    },
    methods:{
        prova(){
            console.log(this.song);
        },
    },
    props:['song'],
}
</script>

<style scoped lang="scss">
@import '../style/general.scss';
@import '../style/variables.scss';
label{
    color: white;
}

</style>