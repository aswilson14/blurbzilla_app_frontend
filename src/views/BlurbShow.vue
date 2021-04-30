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
       <div>
       <button v-on:click="boop">BOOP</button>
       </div>
       <section class="wrapper style1 align-center">
						<div class="inner medium">
							<h2>New Blurb Form</h2>
							<form v-on:submit.prevent="createBlurb()">
								<div class="fields">
									<div class="field">
										<label for="location"
						       >Location</label>
										<input type="text" name="location" id="location" value="" v-model="location" />
									</div>
									
									<div class="field">
										<label for="Blurb Text">New Blurb</label>
										<textarea name="New Blurb" id="blurb-text" rows="4" v-model="newBlurb"></textarea>
									</div>
								</div>
								<ul class="actions special">
									<li><input type="submit" name="submit" id="submit" value="Submit Blurb" /></li>
								</ul>
							</form>

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
    boop: function () {
      location.reload();
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
