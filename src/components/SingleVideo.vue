<template>
    
        <div class="card mb-3 film my_cardsize">
        <div class="card-top">
                            <img :src="getPosterImagePath(`${posterpath}`)" alt="">
        </div>
            <div class="card-body">

                <h5 class="card-title">Titolo:{{ title }}</h5>
                <p class="card-text">Titolo originale:{{originaltitle}}</p>
                <p class="card-text" v-if="!availableLangueges.includes(originallanguage)">{{originallanguage }}></p>
                <div class="flag-image d-flex align-items-center " v-else>
                    <p>Lingua Originale:</p>
                    <img :src="getImagePath(`${originallanguage}.png`)" alt="">
                </div>
                
           
            <div class="d-flex" v-if="getRoundedValue(voteaverage / 2) > 0 && getRoundedValue(voteaverage / 2) <= 1 ">
                <p>Voto:</p>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            </div>
            <div class="d-flex" v-else-if="getRoundedValue(voteaverage / 2) > 1 && getRoundedValue(voteaverage / 2) <= 2 ">
                <p>Voto:</p>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            </div>
            <div class="d-flex" v-else-if="getRoundedValue(voteaverage / 2) > 2 && getRoundedValue(voteaverage / 2) <= 3 ">
                <p>Voto:</p>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            </div>
            <div class="d-flex" v-else-if="getRoundedValue(voteaverage / 2) > 3 && getRoundedValue(voteaverage / 2) <= 4">
                <p>Voto:</p>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            </div>
            <div class="d-flex" v-else-if="getRoundedValue(voteaverage / 2) > 4 && getRoundedValue(voteaverage / 2) <= 5">
                <p>Voto:</p>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
                <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            </div>
            <div v-else>
                <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
                
            </div>
        </div>
</div>


    
</template>
<script>
export default {
    name:"SingleVideo",
    props:{
        title:String,
        originaltitle:String,
        originallanguage:String,
        posterpath:String,
        voteaverage:Number,
        availableLangueges: Array
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
    }
}
</script>
<style lang="scss" scoped>
.film{
    border: 2px solid red;
}
.series{
    border: 2px solid blue;
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
    font-size: 20px;
}

.my_cardsize{
    width: calc((100% / 3) - 1rem);
    margin-right: 0.5rem;
    margin-left: 0.5rem;
    font-size: small;
    img{
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
    
}
.my_cardsize:hover {
    background-color: black;
    color: white;
    
}
.card-body{
    display: none;
} 
.my_cardsize:hover .card-body{
   display: unset;
    
}
.my_cardsize:hover .flag-image img{
   display: unset;
   width: 30px;
   height: 30px; 
}  
.my_cardsize:hover img{
 display: none;
    
}     
    
</style>