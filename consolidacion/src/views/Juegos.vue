<template>
    <div>
        <h1>Los Últimos Juegos</h1>
        <div>
            <button class="btn_games" @click="getData">Juegos</button>
        </div>
        
        <div class="games" v-for="(game, index) in games" :key="index">
            <div>
                <h4>{{game.name}}</h4>
                <img class="imgGame" @click="redirect(game.id)" :src="game.background_image" width="200px" alt="">
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'component-name',
    // props: {},
    data: function(){
        return {
            games: []
        }
    },
    // computed: {},
    methods: {
        getData(){
            axios.get(`https://api.rawg.io/api/games?key=de294bb09054413cb1d75970171acf08&page=1`)
            .then(data=>{
                this.games = data.data.results
                console.log(data.data.results)
            })
        },
        redirect(id){
            
            this.$router.push('/juego/'+id)
        }
    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
.btn_games{
    background-color: rgb(229, 171, 231);
    box-shadow: 0 7px 7px 0 rgb(228, 97, 178), 0 2px 5px 0 rgb(185, 40, 159);
    padding: 10px 10px;
}
h1{
    color: rgb(85, 211, 225);
}
.games{
   
    display: inline-block;
    width: 20%;
    padding: 10PX;
    gap: 10px;
    flex-direction: row;
    justify-content: center;

}
h4{
    color: rgb(234, 218, 228);
    font-family: 'Courier New', Courier, monospace;
    font-weight: bold;
    
   
}
.imgGame{
    border-radius: 45%;
}
    
</style>