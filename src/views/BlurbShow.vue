<template>
  <div class="home">
    <h1>{{ message }}</h1>
    
      
     
     
     	<section class="spotlight style1 orient-right content-align-left image-position-center onscroll-image-fade-in" id="first">
						<div class="content">
							<h2>{{ blurb.location }}</h2>
							<p>{{ blurb.fact }}</p>
						</div>
						<div class="image">
							<img v-bind:src="blurb.image_url" />
						</div>
			 </section>
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
