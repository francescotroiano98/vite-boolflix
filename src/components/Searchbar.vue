<template>
    
        <div class="input-group mt-3 mb-4 w-25 ">
                <span class="input-group-text" id="basic-addon1" @click="$emit('searched', searchedText)">Search a film</span>
                <input type="text" class="form-control" placeholder="Character name" aria-label="Character name" aria-describedby="basic-addon1"  v-model="searchedText"

                @keyup.enter="$emit('searched', searchedText)">
        </div>
    
</template>
<script>
export default {
    data(){
        return{
            searchedText : ''
        }
    },
    name:"Searchbar",

   
}
</script>
<style lang="scss" scoped>

    
</style>