<template>
    <div>
        <Navbar/>
        <Searchbar @searched="searchFilm"/>
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
            seriesList:[],
            apiSeriesUrl:'https://api.themoviedb.org/3/search/tv?api_key=933454d58e05723d1bfb7f8b29528fa2',
            apiFilmUrl:'https://api.themoviedb.org/3/search/movie?api_key=933454d58e05723d1bfb7f8b29528fa2',
            availableLangueges:[
                'it','en','fr','ja','es','cn'
            ]
        
        }
    },
    
    name:"AppHeader",
    components:{
        Navbar,
        Searchbar
    },
    
 


methods: {

    
    getRoundedValue(value) {
    return Math.ceil(value);
  },

    getImagePath: function(img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        },
        getPosterImagePath: function(img) {
            return `http://image.tmdb.org/t/p/w500/${img}`
        },    

        searchFilm(needle = ''){
            axios.get(this.apiFilmUrl, {
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
                }),

                axios.get(this.apiSeriesUrl, {
                    params: {
                        query: needle
                    }
                })
                .then(response => {
                    this.seriesList = response.data.results;
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
.film{
    border: 2px solid red;
}
.series{
    border: 2px solid blue;
}
img{
    width: 20px;
    height: 20px;
}
.posterimage{
    height: 340px;
    width: 226px;
    img{
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
}
.star-size{
    font-size: 50px;
}    
</style>