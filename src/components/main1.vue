<script>
import select1 from './select1.vue';
import card from "./card.vue";
export default {
    name: "main1",
    components:{
        select1,
        card,
    },
    data() {
        return {}
    }
}
</script>
<template>
    <main>
        <!-- <select1 @tipo="$emit='tipo'"></select1> -->
        <select1 @tipo="$emit('tipo')"></select1>
        <card></card>
    </main>
   
</template>
<style lang="scss" scoped>
</style>