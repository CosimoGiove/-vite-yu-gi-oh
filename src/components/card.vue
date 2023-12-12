<script>
import axios from "axios";

export default {
    name: "card",
    data(){
        return{
         cards:[],
        }
    }, 
    created(){
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0")
        .then((data)=>{
          this.cards = data.data.data
        })
    }
}
</script>
<template>
    <div class="contenitorecard">
        <div class="cardtrovate">
            Found 39 card
        </div>
        <div>
            <ul>
                <li v-for="card in cards" class="nomecard">
                    <img :src="card.card_images[0].image_url" alt="">
                   <div> {{ card.name }}</div>
                   <div class="tipologia">{{ card.archetype}}</div>
                </li>
            </ul>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.contenitorecard{
    width: 83%;
    margin: 0 auto;
    padding-top: 45px;
    background-color: white;
    .cardtrovate{
        width: 90%;
        margin: 0 auto;
        background-color: #212529;
        padding: 20px 10px;
        color: white;
    }
    ul {
        display: flex;
        flex-wrap: wrap;
        width: 90%;
        margin: 0 auto;
        justify-content: space-between;
    }
    li{
        flex-basis: calc((100% / 5) - 20px);
        list-style: none;
        margin-bottom: 20px;
    }
    img{
        width: 100%;
    }
    .nomecard{
        background-color:#d48f38 ;
        color: white;
        text-align: center;
        text-transform: uppercase;
    }
    .tipologia{
        color: black;
        margin-top: 20px;
        padding-bottom: 20px;
    }
}
</style>