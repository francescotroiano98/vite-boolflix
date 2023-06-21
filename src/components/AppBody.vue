<template>
    <div>
        <AppHeader/>
        <AppMain/>
    </div>
</template>
<script>

import AppHeader from './AppHeader.vue';
import AppMain from './AppMain.vue';
export default {
    data(){
        return{
           
            filmList:[],
            apiUrl:'https://api.themoviedb.org/3/movie/550?api_key=933454d58e05723d1bfb7f8b29528fa2'
        }
    },
    name:"AppBody",
    components:{
        AppHeader,
        AppMain
    },
    methods:{
    
            
        
},


}

//QUI VOGLIO FARE LA MIA CHIAMATA API //

</script>
<style lang="">
    
</style>