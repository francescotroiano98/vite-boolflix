<template>
    <div>
        <Navbar/>
        <Searchbar @searched="searchFilm"/>
    </div>
    <!--    
        <article class="film" v-for="mysearchedfilm in filmList">
            <div class="posterimage">
                <img :src="getPosterImagePath(`${mysearchedfilm.poster_path}`)" alt="">
            </div>
          

            <h1>{{ mysearchedfilm.title }}</h1>
            <h2>{{ mysearchedfilm.original_title }}</h2>

            <p v-if="!availableLangueges.includes(mysearchedfilm.original_language)">{{ mysearchedfilm.original_language }}</p>
            <img v-else :src="getImagePath(`${mysearchedfilm.original_language}.png`)" alt="">
            <p>{{ getRoundedValue(mysearchedfilm.vote_average / 2) }}</p>
            <div v-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 0 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 1 ">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 1 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 2 ">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 2 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 3 ">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 3 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 4">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 4 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 5">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else>
                <i class="star-size fa-regular fa-star" style="color: #000000;"></i>
                
            </div>
            
            

            
        </article>



        <article class="series" v-for="mysearchedfilm in seriesList">
            <div class="posterimage">
                <img :src="getPosterImagePath(`${mysearchedfilm.poster_path}`)" alt="">
            </div>
            <h1>{{ mysearchedfilm.name }}</h1>
            <h2>{{ mysearchedfilm.original_name }}</h2>

            <p v-if="!availableLangueges.includes(mysearchedfilm.original_language)">{{ mysearchedfilm.original_language }}</p>
            <img v-else :src="getImagePath(`${mysearchedfilm.original_language}.png`)" alt="">


            
      
            <p>{{ getRoundedValue(mysearchedfilm.vote_average / 2) }}</p>
            <div v-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 0 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 1 ">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 1 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 2 ">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 2 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 3 ">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 3 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 4">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else-if="getRoundedValue(mysearchedfilm.vote_average / 2) > 4 && getRoundedValue(mysearchedfilm.vote_average / 2) <= 5">
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else>
                <i class="star-size fa-regular fa-star" style="color: #000000;"></i>
                
            </div>


        </article>
        -->

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