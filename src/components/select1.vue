<script>
import axios from "axios";
import { store } from "../store";
export default {
    data(){
        return{
            store,
        }
    },
    name: "select1",
    created(){
        axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((data) => {
        this.store.selezione = data.data
      })
    },
    methods:{
    }
}
</script>
<template>
    <label for="card"></label>
    <select name="card" id="card" v-model="store.tipologia" @change="$emit('tipo')">
        <option value="">tutti</option>
        <option  v-for="selezioni in store.selezione" :value="selezioni.archetype_name">
            {{ selezioni.archetype_name }}
        </option>
    </select>
</template>
<style lang="scss" scoped>
select {
    width: 150px;
    padding: 10px 5px;
    margin-left: 130px;
    margin-top: 20px;
    margin-bottom: 20px;
}
</style>