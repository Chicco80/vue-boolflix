<template>
<section>
    <h2 class="container">{{title}}</h2>
    <div class="container">
        <div class="row ">
            <div  v-for="item in items" :key="item.id" class="col-4 my-3">
                <div class="card d-flex">
                    <img :src="'https://image.tmdb.org/t/p/w342' + item.poster_path" class="card-img-top" alt="item.name">

                    <div class="overlay d-flex ">
                        <div class="text">{{item.overview}}
                            <div class="card-body">
                                <h5 class="card-title">{{item.original_title ? item.original_title : item.original_name}}</h5>
                                <h5>{{item.title ? item.title : item.name}}</h5>
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
                    </div>
                </div>
            </div>
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

.icons{
    width:25px;
}
ul{
 display: flex;
 justify-content: center;
 list-style-type: none;

}
.debug{
    border: 1px solid red;
}
.card{
    background-color: black;
    height: 100%;
}

.overlay{
    align-items: center;
    height: 100%;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    text-align: center;    
}

.text{
    background: #000000;
    opacity: 0.7;
    height: 100%;
    width: 100%;
    text-align: center;
    position: absolute;
    padding:10px;
    display: none;

}
 .card :hover .text{
     display:block;
}
.card-image-top{
    height: 100%;
    width: 100%;
    position: relative;
}







</style>

https://image.tmdb.org/t/p/w500