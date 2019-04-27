<template>
   <div>
     <form @submit.prevent>
       <label>Zaloguj siê e-mailem</label>
       <input type="email" v-model="email">
       <button @click="enter()">Wchodzê</button>
    </form>
   </div>
</template>

<script>
export default {
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 }
}
</script>