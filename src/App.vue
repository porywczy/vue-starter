<template>
  <div>
   <h1>Witaj w systemie do zapisów na zajęcia</h1>


   <div v-if="email.length > 0">
       <h2>Witaj {{email}}</h2>
       <button @click="logMeOut()">Wyloguj</button>
   </div>
    <div v-else>
        <login-form @login="logMeIn($event)" button-label="Loguję się" header="Loguj"></login-form>
        <login-form @login="logMeIn($event)" button-label="Rejestruję się" header="Rejestruj"></login-form>
    </div>

  </div>
</template>

<script>
    import 'milligram';
    import LoginForm from "./LoginForm";

// to jest wszystko JSON
export default {
    components: {LoginForm},
	 data() {
	     return {
	    	 email: '',
	     };
	},
    methods: {
	     //docelowo stan od decyzji serwera
        logMeIn(username) {
            //odwolanie do stanu komponentu dlatego this
            this.email = username;
          },
        logMeOut() {
            //odwolanie do stanu komponentu dlatego this
             this.email = '';
        }
    }
}
</script>

<style>
/* commented */
</style>
