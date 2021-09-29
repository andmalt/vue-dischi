<template>
    <div id="load" class="row justify-content-center align-items-center">
         <div  class="col-12 col-sm-6 col-lg-4 d-flex flex-column justify-content-center align-items-center">
            <div id="bar"></div>
            <h1>Loading....</h1>
        </div>  
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import '../style/general.scss';
@import '../style/variables.scss';

#load{  
    height: 100%;
    & h1{
        color: $titleColor;
    }
}
#bar{
    height: 12rem;
    width: 1rem;
    background-color: whitesmoke;
    animation: loading 1s linear infinite;

    @keyframes loading {
        from {
            transform: rotate(0deg);
        }
        to{
            transform: rotate(360deg);
        }
    }
}
</style>