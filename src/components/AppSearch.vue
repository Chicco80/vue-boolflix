<template>
<div class="py-2">
    <input type="text" v-model='search' @keyup.enter="$emit('performSearch', search)">
    <button @click="cerca">cerca</button>  
</div>  
</template>
<script>

export default {
    name:'AppSearch',
    data(){
        return{
            search:'',
            
        }

    },
    computed:{
        
        
        
    },
    methods:{
        cerca(){
            this.$emit('performSearch', this.search)
            this.search = ''
        }
    }
}
</script>

<style lang="scss" scoped>

</style>