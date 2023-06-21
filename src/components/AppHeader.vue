<template>
    <div>
        <Navbar/>
        <Searchbar/>
    </div>
</template>
<script>

import Navbar from './navbar.vue'
import Searchbar from './Searchbar.vue'
export default {
    
    name:"AppHeader",
    components:{
        Navbar,
        Searchbar
    },
    
 
}


</script>
<style lang="">
    
</style>