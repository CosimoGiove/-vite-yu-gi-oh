<script>
import axios from "axios";
import { store } from "./store";
import header1 from './components/header1.vue';
import main1 from './components/main1.vue';
export default {
  data() {
    return {
    }
  },
  components: {
    header1,
    main1,
  },
  created() {
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0")
      .then((data) => {
        store.cards = data.data.data
      })
  }
}

</script>

<template>
  <header1></header1>
  <main1></main1>
</template>

<style lang="scss" scoped>
@use 'style.scss' as *;
</style>
