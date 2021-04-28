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
       <form v-on:submit.prevent="createBlurb()">
								<div class="fields">
                    
									<div class="field half">
										<label for="name">Location</label>
										<input type="text" name="name" id="name" value="" v-model="location"/>
									</div>
									
									<div class="field">
										<label for="message">New Blurb</label>
										<textarea name="message" id="message" rows="6" v-model="newBlurb"></textarea>
									</div>
								</div>
								<ul class="actions special">
									<button>Submit Blurb</button>
                                    
								</ul>
							</form>
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
      newBlurb: "",
      location: "",
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

    createBlurb: function () {
      console.log("creating blurb...");
      var params = {
        location: this.location,
        blurb: this.newBlurb,
      };
      axios.post("/api/blurbs", params).then((response) => {
        console.log("blurbs create", response);
        this.location = "";
        this.newBlurb = "";
      });
    },
  },
};
</script>
