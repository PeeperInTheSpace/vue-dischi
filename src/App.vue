<template>
  <div id="app">
    <HeaderSection @filter="assignFilter" />
    <MainSection :exportedArray = applyFilter />
  </div>
</template>

<script>
import HeaderSection from './components/HeaderSection.vue';
import MainSection from './components/MainSection.vue';
import axios from "axios";

export default {
  name: 'App',
  components: {
    HeaderSection,
    MainSection
},

data () {

return {

  musicArray: [],
  filter: "All"

}

},

methods: {

  assignFilter (genreSelect) {

    this.filter = genreSelect
    console.log(this.filter)

  }

},

computed: {

  applyFilter () {

    let array = []
    this.musicArray.forEach(item => {
      
      if (this.filter === item.genre) {

        array.push(item)

      } else if (this.filter === "All") {

        array = this.musicArray

      }

    });

    return array

  }

},

created () {
  axios.get("https://flynn.boolean.careers/exercises/api/array/music")
  .then((response) => {

    this.musicArray = response.data.response

  })
}

}
</script>

<style lang="scss">

@import "./style/common.scss"; 

</style>
