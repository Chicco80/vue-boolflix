<template>
    <section>
        <h2>{{title}}</h2>
    <ul>
        <li v-for="item in items" :key="item.id">
        id: {{item.id}}
        {{item.original_title ? item.original_title : item.original_name}}
        {{item.title ? item.title : item.name}}
        <div v-if="item.original_language">
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