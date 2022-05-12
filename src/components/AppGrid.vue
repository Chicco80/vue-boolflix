<template>
    <section>
        <h2 class="container">{{title}}</h2>
            <div class="container debug ">
                <div class="row">
                    <ul class=" d-flex flex-wrap">
                        <li v-for="item in items" :key="item.id">
                            <div class="cont-poster">
                                <img class="p-3 poster " :src="'https://image.tmdb.org/t/p/w342' + item.poster_path" alt="item.name">
                            <div class="overlay d-flex p-3">
                                <div class="text">{{item.overview}}</div>
                            </div>
                            <div class="card-body debug">
                                <h2> {{item.original_title ? item.original_title : item.original_name}}</h2>
                                <h4> {{item.title ? item.title : item.name}}</h4>
                            <div v-if="item.original_language == 'en' && 'it'">
                                <img :src="'../img/'+ item.original_language + '.png'" alt="item.name" class="icons">
                            </div>
                            <div v-else>
                                <img :src="'../img/an.png'" alt="item.name" class="icons">
                            </div>
                            <span v-for="(n, index) in 5" :key="index">
                                <i :class=" n <= showStar(item) ? 'fa-solid fa-star text-warning' : 'fa-regular fa-star'"></i>
                            </span>
                            </div>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
    </section> 
</template>

<script>
export default {
    name:'AppGrid',
    props:['items','title'],
    data(){
        return{

        }
    },
    methods:{
        showStar(item){
            return parseInt(item.vote_average / 2);
            
        }
    },

    
}
</script>

<style lang="scss" scoped>
#app{
    height: 100vh;
    width: 100%;
}
// img{
//     width: 347px;
// }
.icons{
    width:20px;
}
ul{
 display: flex;
 justify-content: center;
 list-style-type: none;

}
.debug{
    border: 1px solid red;
}
.card-body{

    width: 342px;
    
}

.overlay{
    position: absolute;
    top: 0;
    left: 0;
    width: 342px;
    text-align: center;    
}

.text{
    text-align: center;
    position: absolute;
    opacity: 1;
    padding-left: 20px;
    display: none;

}
.cont-poster :hover .text{
    display:block;
}
.cont-poster{
    width: 100%;
    position: relative;
}







</style>

https://image.tmdb.org/t/p/w500