<template>
  <div>
    <input v-model="buckeysInput" />
    <button @click="buckeysMethod">My Post Request</button>
    <img :src="poster" />
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Input",
  methods: {
    buckeysMethod: function() {
      var outerThis = this;
      var title = this.buckeysInput.replace(" ", "+").replace(" ", "+");
      
      axios
        .get(`http://www.omdbapi.com/?t=${title}&apikey=400ae623`)
        .then(function(response) {
            outerThis.poster = response.data.Poster
        })
        .catch(function(e) {
          console.log(e);
        });
    }
  },
  data() {
    return {
      buckeysInput: "",
      poster: "",

    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
