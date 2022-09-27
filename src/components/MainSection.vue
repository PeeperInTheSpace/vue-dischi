<template>
    <main>
        <section class="container d-flex flex-wrap justify-content-center h-100 align-items-center">
            <div class="fl-card d-flex align-items-center flex-column p-3 text-center gap-3 rounded-4" v-for="(item) in exportedArray" :key="item.poster">
                <img :src="item.poster" alt="album-cover">
                <h3>{{ item.title }}</h3>
                <h4 class="fl-grey">{{ item.author }}</h4>
                <h4 class="fl-grey">{{ item.year }}</h4>
            </div>
        </section>
    </main>
</template>

<script>
export default {
    name:"MainSection",
    props: {
        exportedArray: Array
    }
}
</script>

<style lang="scss" scoped>

    main {
        background-color: #1e2d3b;
        height: 90vh;
        color: white;
    }

    .fl-card {
        width: calc(100% / 5 - 30px);
        height: 400px;
        margin: 15px;
        background-color: #2e3a46;

        img {
            height: 150px;
            width: 150px;
        }

    }

    .fl-grey {
        color: grey;
    }

</style>