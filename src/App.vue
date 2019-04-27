<template>
  <div>
   <h1>Witaj w systemie do zapisów na zajęcia</h1>


   <div v-if="isAuthenticated">
       <h2>Witaj {{email}}</h2>
       <button @click="logMeOut()">Wyloguj</button>
   </div>
    <div v-else>
        <p>Zaloguj sie emailem
        <input type="text" v-model="email">
        <button @click="logMeIn()">Wchodzę</button>
        </p>
    </div>

  </div>
</template>

<script>

// to jest wszystko JSON
export default {
	 data() {
	     return {
	    	 email: '',
	    	 isAuthenticated: false
	     };
	},
    methods: {
	     //docelowo stan od decyzji serwera
        logMeIn() {
            //odwolanie do stanu komponentu dlatego this
            this.isAuthenticated = true;
        },
        logMeOut() {
            //odwolanie do stanu komponentu dlatego this
            this.isAuthenticated = false;
            this.email = '';
        }
    }
}
</script>

<style>
/* commented */
</style>
