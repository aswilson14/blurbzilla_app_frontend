<template>

  <div id="wrapper">
	  <div id="nav">
	  <router-link to="/Signup">Signup</router-link> ||
	  <router-link to="/Login">Login</router-link> ||
	  <router-link to="/Logout">Logout</router-link>
	  </div>
   <router-view/>
  
        
				<!-- Seven -->
					
          
				<!-- Footer -->
					<footer class="wrapper style1 align-center">
						<div class="inner">
							<ul class="icons">
								<li><a href="#" class="icon brands style2 fa-twitter"><span class="label">Twitter</span></a></li>
								<li><a href="#" class="icon brands style2 fa-facebook-f"><span class="label">Facebook</span></a></li>
								<li><a href="#" class="icon brands style2 fa-instagram"><span class="label">Instagram</span></a></li>
								<li><a href="#" class="icon brands style2 fa-linkedin-in"><span class="label">LinkedIn</span></a></li>
								<li><a href="#" class="icon style2 fa-envelope"><span class="label">Email</span></a></li>
							</ul>
							<p>&copy; Untitled. Design: <a href="https://html5up.net">HTML5 UP</a>.</p>
						</div>
					</footer>

			</div>

</template>
<script>
import Form from "./components/Form.vue";

export default {
  name: "app",
  components: {
    Form,
  },
};
</script>

<style>
</style>
