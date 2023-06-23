<template>

<!--QUESTO PER LE SERIE-->
<div class="card mb-3 film my_cardsize series">
    <div class="card-top">
                        <img :src="getPosterImagePath(`${posterpathserie}`)" alt="">
    </div>
        <div class="card-body">

            <h5 class="card-title">Titolo:{{ titleserie }}</h5>
            <p class="card-text">Titolo originale:{{originaltitleserie}}</p>
            <p class="card-text" v-if="!availableLangueges.includes(originallanguageserie)">{{originallanguageserie}}></p>
            <div class="flag-image d-flex align-items-center mb-2" v-else>
                
                    <p class="m-0 me-2">Lingua Originale:</p>
            
                    <img :src="getImagePath(`${originallanguageserie}.png`)" alt="">
                
            </div>
            
       <!--VOGLIO RENDERE PIU' LEGGIBILE LA PARTE SOTTO -->


        <div class="d-flex" v-if="getRoundedValue(voteaverageserie / 2) > 0 && getRoundedValue(voteaverageserie / 2) <= 1 ">
            <p class="me-2">Voto:</p>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
        </div>
        <div class="d-flex" v-else-if="getRoundedValue(voteaverageserie / 2) > 1 && getRoundedValue(voteaverageserie / 2) <= 2 ">
            <p class="me-2">Voto:</p>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
        </div>
        <div class="d-flex" v-else-if="getRoundedValue(voteaverageserie / 2) > 2 && getRoundedValue(voteaverageserie / 2) <= 3 ">
            <p class="me-2">Voto:</p>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
        </div>
        <div class="d-flex" v-else-if="getRoundedValue(voteaverageserie / 2) > 3 && getRoundedValue(voteaverageserie / 2) <= 4">
            <p class="me-2">Voto:</p>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size star-size fa-solid fa-star" style="color: #ffdd00;"></i>
            <i class="star-size fa-regular fa-star" style="color: #ffffff;"></i>
        </div>
        <div class="d-flex" v-else-if="getRoundedValue(voteaverageserie / 2) > 4 && getRoundedValue(voteaverageserie / 2) <= 5">
            <p class="me-2">Voto:</p>
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
name:"SingleVideoSerie",
props:{
    titleserie:String,
    originaltitleserie:String,
    originallanguageserie:String,
    posterpathserie:String,
    voteaverageserie:Number,
    availableLangueges: Array,

},
methods: {


            getRoundedValue(value) {
            return Math.ceil(value);
            },

            getImagePath: function(img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
            },

            getPosterImagePath: function(img) {
            return `http://image.tmdb.org/t/p/w342/${img}`
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
.flag-image p{
height: 25px;
}
.star-size{
font-size: 20px;
}

.my_cardsize{
width: calc((100% / 4) - 1rem);
margin-right: 0.5rem;
margin-left: 0.5rem;

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