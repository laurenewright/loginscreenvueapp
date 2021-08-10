<template>
  <Header/>
  <LoginForm/>
  <SignupForm/>
</template>

<script>
import Header from "./components/Header.vue"
import SignupForm from "./components/SignupForm.vue"
import LoginForm from "./components/LoginForm.vue"

export default {
  name: 'App',
  components: {
    Header,
    SignupForm,
    LoginForm
  }
}
</script>

<style>
</style>


