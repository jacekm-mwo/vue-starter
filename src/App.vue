<template>
  <div>
    <h1>elo</h1>
    
    <!--  comment -->
    
    <p> {{ email }} </p>
   
    <div v-if="email.length > 0">
    <logged-in-page :username="email"
                     @logout="loggedOut()" > </logged-in-page>
                     
    </div>
    <div v-else>

		<login-form @login="loggedIn($event)":button-label="'klikaj'"
		:header="'header1'"></login-form>
		
		<login-form @login="enter($event)" :button-label="'Wleæ'"
		:header="'head'"></login-form>

		
        <login-form @login="enter($event)":button-label="'Zaloguj siê jak cz³owiek'"
         :header="'last'"></login-form>

    </div>
    
</div>
  
  
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";
import LoggedInPage from "./LoggedInPage";

export default {
	components: {LoginForm, LoggedInPage}, 
	
	data() {
		  return {
		    email: '',
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
				  this.email = '';
			  }
		}
		
	
}


</script>

<style>

</style>
