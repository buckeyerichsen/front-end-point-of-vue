<template>
  <div>
    <input v-model="personsName" />
    <button @click="javaRequest">name</button>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "Input",
  methods: {
    javaRequest: function() {
      var outerThis = this;
      
      axios
        .get(`http://192.168.0.102:8080/greeting?name=${this.personsName}`)
        .then(function(response) {
            console.log(response.data)
        })
        .catch(function(e) {
          console.log(e);
        });
    }
  },
  data() {
    return {
      personsName: "",

    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>