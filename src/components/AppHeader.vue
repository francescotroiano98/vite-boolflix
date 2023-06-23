<template>
    <div class="bg-black d-flex justify-content-between px-4 py-2">
        <Navbar/>
        <Searchbar @searched="searchFilm"/>
    </div>

</template>
<script>
import axios from 'axios';
import Navbar from './navbar.vue'
import Searchbar from './Searchbar.vue'
import {store} from '../store'
export default {
    data(){
        return{
            store,
            filmList:[],
            seriesList:[],
            apiSeriesUrl:'https://api.themoviedb.org/3/search/tv?api_key=933454d58e05723d1bfb7f8b29528fa2',
            apiFilmUrl:'https://api.themoviedb.org/3/search/movie?api_key=933454d58e05723d1bfb7f8b29528fa2',
            
        
        }
    },
    
    name:"AppHeader",
    components:{
        Navbar,
        Searchbar
    },
    
 


        methods: {

            searchFilm(needle = ''){
            axios.get(this.apiFilmUrl, {
                    params: {
                        query: needle
                    }
                })
                .then( (response) => {

                    this.filmList = response.data.results;
                    this.store.filmList = response.data.results;

                    console.log(this.filmList)
                    

                })
                .catch(function (error) {
                    console.log(error);
                }),

                axios.get(this.apiSeriesUrl, {
                    params: {
                        query: needle
                    }
                })
                .then(response => {
                    this.seriesList = response.data.results;
                    this.store.seriesList = response.data.results;
                    console.log(this.seriesList);
                })
                .catch(error => {
                    console.log(error);
                });

            }
        },


        created(){
            this.searchFilm();
        }
}

</script>

<style lang="scss">

 
</style>