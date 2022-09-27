<template>
  <header class="d-flex align-items-center justify-content-between px-3">
    <img src="../assets/spotify_logo.png" alt="logo">
    <select @change="$emit('filter', genreSelect)" class="h-50 w-25 rounded-pill fs-3 text-center" v-model="genreSelect">
        <option value="All">All</option>      
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <option value="Pop">Pop</option>
        <option value="Rock">Rock</option>
    </select>
  </header>
</template>

<script>
export default {
    name: "HeaderSection",
    data () {
        return {

            genreSelect: "All"

        }
    }
}
</script>

<style lang="scss" scoped>

    header {
        background-color: #2e3a46;
        height: 10vh;

        img {
            height: 80%;
        }

    }

</style>