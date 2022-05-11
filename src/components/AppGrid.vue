<template>
    <section>
        <h2>{{title}}</h2>
    <ul>
        <li v-for="item in items" :key="item.id">
        <img :src=" apiImg + item.poster_path" alt="">
        id: {{item.id}}
        {{item.original_title ? item.original_title : item.original_name}}
        {{item.title ? item.title : item.name}}
        <div v-if="item.original_language == 'en' && 'it'">
        <img :src="'../img/'+ item.original_language + '.png'" alt="item.name">
        </div>
        <div v-else>
            <img :src="'../img/eu.png'" alt="item.name">
        </div>
        <!-- {{item.original_language}} -->
        {{item.vote_average}}
        </li>
    </ul>
    </section>
</template>

<script>
export default {
    name:'AppGrid',
    props:['items','title'],
    data(){
        return{

        }
    }

    
}
</script>

<style lang="scss" scoped>

</style>

//https://image.tmdb.org/t/p/w500