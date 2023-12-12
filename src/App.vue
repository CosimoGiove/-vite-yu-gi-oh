<script>
import axios from "axios";
import { store } from "./store";
import header1 from './components/header1.vue';
import main1 from './components/main1.vue';
export default {
  data() {
    return {
      loading: true
    }
  },
  components: {
    header1,
    main1,
  },
  created() {
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=500&offset=0")
      .then((data) => {
        store.cards = data.data.data
      })
  },
  methods: {
    fetchData() {
      // Replace with your API call
      fetch("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=500&offset=0")
        .then((response) => response.json())
        .then((data) => {
          // Handle your data here
          this.loading = false;
        })
        .catch((error) => {
          console.error("Error fetching data:", error);
          this.loading = false;
        });
    },
  },
  mounted() {
    this.fetchData();
  },
}

</script>

<template>
   <div class="app">
    <div class="loading-screen" v-if="loading">
      <p>Loading...</p>
    </div>
    <div class="content" v-if="!loading">
      <header1></header1>
      <main1></main1>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use 'style.scss' as *;

.loading-screen {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  font-size: 50px;
  background-color: #fff;
  z-index: 99;
}
</style>
