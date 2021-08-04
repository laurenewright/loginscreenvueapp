<template>
  <div id="loginForm" class="col-4 mx-auto float-right">
    <form @submit="checkLoginForm" method="post" class="col-4 mx-auto text-center">
      <h4>Login Form</h4>
      <p v-if="loginErrors.length">
        <b>Please correct the following error(s):</b>
        <ul>
          <li v-bind:key="loginError" v-for="loginError in loginErrors">{{ loginError }}</li>
        </ul>
      </p>
      <p class="justify-content-md-center">
        Email
      </p>
      <input type="email" v-model="loginEmail" placeholder="Email" id="loginEmail" class="justify-content-md-center">
      <p class="justify-content-md-center">
        Password
      </p>
      <input type="password" v-model="loginPassword" placeholder="Password" id="loginPassword" class="justify-content-md-center" minlength="8">
      <p>
        <input type="submit" value="Login" name="login" class="justify-content-md-center">
      </p>
    </form>
    <p class="col-4 mx-auto text-center" id="signupButton">
      <button @click="signupButton();">
        Sign Up
        </button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'LoginForm',
  el: "#loginForm",
  data: function (){
    return{
    loginErrors:[],
    loginEmail:null,
    loginPassword:null
    };
  },
  methods:{
    checkLoginForm:function(event){
      // if there is an email and password present
      if(this.loginEmail && this.loginPassword){
        alert("Thank you for testing!");
      }
      this.loginErrors = [];
      console.log("hey login")
      // if there is not a password entered
      if(!this.loginPassword) {
        this.loginErrors.push("Password Required.");
      }
      // if there is not an email entered
      if(!this.loginEmail){
        this.loginErrors.push("Email Required.");
      }
      // prevents the page from reloading when submit is clicked
      event.preventDefault();
    },
    // showing sign up div and hiding login div
    // function showSignupForm() {
    //     // show signup form div
    //     document.getElementById('signupForm').style.display= "block";
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
