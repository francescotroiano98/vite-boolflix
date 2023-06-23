<template>
    <div class="carta-del-film container d-flex flex-wrap">
        <SingleVideo v-for="filmvideo in store.filmList"
        
        :title="filmvideo.title"
        :originaltitle="filmvideo.original_title"
        :originallanguage="filmvideo.original_language"
        :voteaverage="filmvideo.vote_average"
        :posterpath="filmvideo.poster_path"
        :availableLangueges="store.availableLangueges"
                                                        />
    </div>
</template>
<script>
import SingleVideo from './SingleVideo.vue';
import {store} from '../store'
export default {
    data(){
        return{
            store,
        }

    },
    name:"VideoList",
    components:{
        SingleVideo
    }
}
</script>
<style lang="">
    
</style>