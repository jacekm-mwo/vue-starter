<template>
  <div>
    
	    <p> zalogowany jako {{ username }} </p>
	    <button @click="$emit('logout')">wyloguj</button>

  </div>
</template>


<script>
export default {
 props: ['username']
}
</script>