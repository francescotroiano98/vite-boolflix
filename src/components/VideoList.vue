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
        <SingleVideoSerie v-for="serievideo in store.seriesList"
        
        :titleserie="serievideo.name"
        :originaltitleserie="serievideo.original_name"
        :originallanguageserie="serievideo.original_language"
        :voteaverageserie="serievideo.vote_average"
        :posterpathserie="serievideo.poster_path"
        :availableLangueges="store.availableLangueges"
        
                                                        />

    </div>
</template>
<script>
import SingleVideo from './SingleVideo.vue';
import SingleVideoSerie from './SingleVideoSerie.vue';
import {store} from '../store'
export default {
    data(){
        return{
            store,
        }

    },
    name:"VideoList",
    components:{
        SingleVideo,
        SingleVideoSerie
    }
}
</script>
<style lang="">
    
</style>