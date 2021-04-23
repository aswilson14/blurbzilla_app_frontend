<template>
  <div class="home">
    <h1>{{ message }}</h1>
    
     <h2>{{ blurb.location }}</h2> 
     <img v-bind:src="blurb.image_url" />
     <p>{{ blurb.fact }}</p>
     
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      blurb: {},
      message: "BlurbZilla",
    };
  },
  created: function () {
    this.indexBlurbs();
  },
  methods: {
    indexBlurbs: function () {
      axios.get("api/blurbs").then((response) => {
        console.log("blurbs index", response);
        this.blurb = response.data;
      });
    },
  },
};
</script>
