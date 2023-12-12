<script>
import { store } from "../store";
export default {
    name: "card",
    data() {
        return {
            store,
        }
    },
}
</script>
<template>
    <div class="contenitorecard">
        <div class="cardtrovate">
            Found {{ store.cards.length }} card
        </div>
        <div>
            <ul>
                <li v-for="card in store.cards" class="nomecard">
                    <img :src="card.card_images[0].image_url" alt="">
                    <div> {{ card.name }}</div>
                    <div class="tipologia">{{ card.archetype }}</div>
                </li>
            </ul>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.contenitorecard {
    width: 83%;
    margin: 0 auto;
    padding-top: 45px;
    background-color: white;

    .cardtrovate {
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

    li {
        flex-basis: calc((100% / 5) - 20px);
        list-style: none;
        margin-bottom: 20px;
    }

    img {
        width: 100%;
    }

    .nomecard {
        background-color: #d48f38;
        color: white;
        text-align: center;
        text-transform: uppercase;
    }

    .tipologia {
        color: black;
        margin-top: 20px;
        padding-bottom: 20px;
    }
}</style>