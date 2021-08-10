<template>
  <div id="signupForm" class="col-4 mx-auto float-right">
    <form @submit="checkSignupForm"  method="post" class="col-4 mx-auto text-center">
      <h4>Signup Form</h4>
      <p v-if="signupErrors.length">
        <b>Please correct the following error(s):</b>
        <ul>
          <li v-bind:key="signupError" v-for="signupError in signupErrors">{{ signupError }}</li>
        </ul>
      </p>
      <p class="justify-content-md-center">
        Email
      </p>
      <input type="email" v-model="signupEmail" placeholder="Email" id="signUpemail" class="justify-content-md-center">
      <p class="justify-content-md-center">
        Password
      </p>
      <input type="password" v-model="signupPassword" placeholder="Password" id="signupPassword" class="justify-content-md-center" minlength="8">
      <p class="justify-content-md-center">
        Password Confirmation
      </p>
      <input type="password" v-model="signupPasswordConfirmation" placeholder="Password" id="signUpPasswordConfirmation" class="justify-content-md-center" minlength="8">
      <p>
        <input type="submit" value="Signup" name="signup" class="justify-content-md-center">
      </p>
    </form>
      <p class="col-4 mx-auto text-center" id="loginButton">
      <button v-on:click="loginButton">
        Login
      </button>
      </p>
  </div>
</template>

<script>
export default {
  name: 'SignupForm',
  el: "#signupForm",
  data: function (){
    return{
    signupErrors:[],
    signupPassword:null,
    signupPasswordConfirmation: null,
    signupEmail:null
    };
  },
  methods:{
    loginButton: function(){
      console.log ("there was an error 2")
      document.getElementById('signupForm').style.display= "none";   
      document.getElementById('loginForm').style.display= "block"; 
      this.signupErrors.splice(0);
    },
    checkSignupForm:function(event){
      this.signupErrors = [];
      console.log("signing up for lvl up  conf")
      // if there is not an email entered
      if(!this.signupEmail){
        this.signupErrors.push("Email Required.");
      }
      // if there is not a password entered
      if(!this.signupPassword) {
        this.signupErrors.push("Password Required.");
      }
      // if there is not a password confirmation entered
      if(!this.signupPasswordConfirmation) {
        this.signupErrors.push("Password Confirmation Required.");
      }
      // if the password and password confirmation do not match
      if(this.signupPassword != this.signupPasswordConfirmation){
        this.signupErrors.push("Passwords don't match!");
      }
      // if there is an email and the password and password confimation match, display message
      if(this.signupEmail && this.signupPassword === this.signupPasswordConfirmation){
        alert("Thank you for testing!");
      }
      // prevents the page from reloading when submit is clicked
      event.preventDefault();
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
