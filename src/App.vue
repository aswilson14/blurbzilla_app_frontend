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
#wrapper {
  background-image: url("https://i.pinimg.com/originals/ef/19/29/ef1929f8e11b1408ee388e51f09e8d88.jpg");
}
#second {
  border: 5px solid rgb(197, 190, 190);
  border-radius: 5px;
  padding: 5px;
  display: block;
  margin-left: 25%;
  margin-right: 50%;
  width: 50%;
  height: relative;
}

#nav {
  float: center;
  display: block;
  color: #968c8c;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
  border-bottom: 3px solid transparent;
}

#blurbs {
  margin: auto;
  width: 65%;
  border: 2px solid rgb(8, 44, 8);
  padding: 15px;
}

#boop {
  margin: 0;
  position: absolute;
  top: 25%;
  left: 6%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
</style>
