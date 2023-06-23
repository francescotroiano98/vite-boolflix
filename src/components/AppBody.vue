<template>
    <body>
        <AppHeader/>
        <AppMain/>
    </body>
        
    
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

</script>
<style lang="scss" scoped>

body{
   
    width: 100vw;
    background-color: gray;
}
    
</style>