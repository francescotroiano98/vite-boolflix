<template>
    <div>
        <AppHeader/>
        <AppMain/>
    </div>
</template>
<script>
import axios from 'axios';
import AppHeader from './AppHeader.vue';
import AppMain from './AppMain.vue';
export default {
    data(){
        return{
           
            filmList:[],
            apiUrl:'https://api.themoviedb.org/3/search/movie?api_key=933454d58e05723d1bfb7f8b29528fa2'
        }
    },
    name:"AppBody",
    components:{
        AppHeader,
        AppMain
    },
    methods:{
        
        getAllVideos(){
            axios.get(this.apiUrl, {
                params:{
                    num: 20,
                    offset: 0,
                   
                }
            })
            .then( (response) => {
                    // handle success
                    this.filmList = response;
                    console.log(this.filmList);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }
           
            
        
},

created(){
    this.getAllVideos()
}
}

//QUI VOGLIO FARE LA MIA CHIAMATA API //

</script>
<style lang="">
    
</style>