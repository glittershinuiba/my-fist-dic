

<template>
  <div class="container">
    <div class="form-inline">
      <input @keyup.enter="onSubmit($event)"
        v-model="word"
        autofocus
        class="form-control mr-sm-2"
        type="onsubmit"
        placeholder="hello there"
        id="inputDefault"
      >
      <button class="btn btn-primary" v-on:click="axios">search</button>
    </div>
    <div class="jumbotron" v-for="def in defs" v-bind:key="def.defid">
      <h1 class="display-3">{{ def.word }}</h1>
      <p class="lead">{{ def.definition }}</p>
      <hr class="my-4">
      <p>{{ def.example }}</p>
      <p class="lead">
        <a class="btn btn-primary btn-lg" :href="def.permalink" role="button">Learn more</a>
      </p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Input",
  data() {
    return {
      defs: "",
      word: ""
    };
  },
  methods: {
    axios: function() {
      axios
        .get(`http://api.urbandictionary.com/v0/define?term=${this.word}`)
        .then(response => {
          var data = response.data;
          this.defs = data.list;
        })
        .catch(function(error) {
          console.log(error);
        })
        .then(function() {
          //
        });
    },
  onSubmit: function(e) {
      axios
        .get(`http://api.urbandictionary.com/v0/define?term=${e.target.value}`)
        .then(response => {
          var data = response.data;
          this.defs = data.list;
        })
        .catch(function(error) {
          console.log(error);
        })
        .then(function() {
          //
        });
     }
}
}
</script>

<style>
input {
  margin-right: 5px;
}

.form-inline {
  display: flex;
  justify-content: center;
}

.jumbotron {
  background-attachment: fixed;
  text-align: left;
  block-size: auto;
  margin: 15px;
}
</style>

