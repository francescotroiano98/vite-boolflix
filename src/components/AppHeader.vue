<template>
    <div>
        <Navbar/>
        <Searchbar @searched="searchFilm"/>
        <article class="film" v-for="mysearchedfilm in filmList">
            <h1>{{ mysearchedfilm.title }}</h1>
            <h2>{{ mysearchedfilm.original_title }}</h2>
            <img :src="getImagePath(`${mysearchedfilm.original_language}.png`)" alt="">


            <p>{{ mysearchedfilm.original_language }}</p>

      
            <p>{{ mysearchedfilm.vote_average }}</p>


        </article>
        
    </div>
</template>
<script>
import axios from 'axios';
import Navbar from './Navbar.vue'
import Searchbar from './Searchbar.vue'
export default {
    data(){
        return{
            filmList:[],
            apiUrl:'https://api.themoviedb.org/3/search/movie?api_key=933454d58e05723d1bfb7f8b29528fa2',
            defaultImagePath: '../assets/img/default.png'
        }
    },
    
    name:"AppHeader",
    components:{
        Navbar,
        Searchbar
    },
    
 


methods: {

    getImagePath: function(img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        },

        searchFilm(needle = ''){
            axios.get(this.apiUrl, {
                    params: {
                        query: needle
                    }
                })
                .then( (response) => {

                    this.filmList = response.data.results;

                    console.log(this.filmList)
                    

                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },


    created(){
        this.searchFilm();
    }
}
</script>
<style lang="scss">
.film{
    border: 2px solid red;
}
img{
    width: 20px;
    height: 20px;
}
    
</style>