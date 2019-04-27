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
	    <input type="text" v-model="email">
	    <button @click="loggedIn">zaloguj</button>
	    
	    <div v-if="email.length < 10">Ale masz krotki adres!</div>
	    <div v-else-if="email.length < 15">Twoj adres e-mail jest w sam raz.</div>
	    <div v-else>Twoj adres e-mail jest stanowczo za dlugi.</div>
	    <p> {{ email }} </p>
    
    </div>
    
</div>
  
  
</template>

<script>

import "milligram";



export default {
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
		  
		  loggedIn() {
			    this.loggedInVar = true
			  },
		  loggedOut(){
				  this.loggedInVar = false
			  }
		}
		
	
}


</script>

<style>

</style>
