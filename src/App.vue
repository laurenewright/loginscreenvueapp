<template>
  <Header/>
  <!-- <LoginForm/> -->
  <SignupForm/>
</template>

<script>
import Header from "./components/Header.vue"
import SignupForm from "./components/SignupForm.vue"
// import LoginForm from "./components/LoginForm.vue"

export default {
  name: 'App',
  components: {
    Header,
    SignupForm,
    // LoginForm,
  }
}
</script>

<style>

/* #signupForm {
    display: none;
  } */

/* body {
    background-image: url("assets/LevelUpConfDesktop.jpg");
    background-size:cover;
    background-repeat: no-repeat;
    background-color: #8AB9E8;
  }

  #loginForm, #signupForm {
    position: absolute;
    bottom: 0;
    right: 0;
  }

  li {
    list-style: none;
  } */
</style>


