<template>
    <form class="d-flex justify-content-center pb-3"  v-on:submit.prevent>
        <label for="genre">Seleziona un genere</label>
        <select v-model="options" name="genre" class="ms-3" id="selector">
            <option v-for="element in song" :key="element" :value="element" @click="$emit('choise',options)">{{ element }}</option>
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
            console.log(this.options);
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