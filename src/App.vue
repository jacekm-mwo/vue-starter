<template>
  <div>
    <h1>elo</h1>
    
    <!--  comment -->
    
    <p> {{ email }} </p>
   
    <div v-if="loggedInVar">
	    <p> zalogowany jako {{ email }} </p>
	    <button @click="loggedOut">wyloguj</button>
	    
    </div>
    <div v-else>

		<login-form @login="loggedIn($event)"></login-form>
    </div>
    
</div>
  
  
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";


export default {
	components: {LoginForm},
	data() {
		  return {
		    email: 'jacek@jacekm.com',
		    password: '',
		    loggedInVar: false
		  };
		},
	
	methods: {
		  alertMyEmail() {
		    alert(this.email);
		  },
		  
		  loggedIn(username) {
			    this.email = username;
			    this.loggedInVar = true;
			  },
		  loggedOut(){
				  this.loggedInVar = false;
			  }
		}
		
	
}


</script>

<style>

</style>
