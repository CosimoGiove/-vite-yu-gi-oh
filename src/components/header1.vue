<script>
export default {
    name: "header1",
    data() {
        return {
            url: "https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es"
        }
    }
}
</script>
<template>
    <header>
        <div><img :src="url" alt="logo"></div>
        <h1>Yu-Gi-Oh Api</h1>

    </header>
</template>
<style lang="scss" scoped>
header {
    display: flex;
    align-items: center;
    margin: 17px 25px;
}

img {
    width: 65px;
}
h1{
    margin-left: 20px;
}
</style>