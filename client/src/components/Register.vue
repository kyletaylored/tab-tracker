<template>
  <div>
    <h1>Register</h1>

    <input type="email" name="email" value="" placeholder="Enter email..."
    v-model="email">
    <input
    type="password"
    name="password"
    placeholder="Password"
    v-model="password">
    <button
    type="button" name="register"
    @click="register()">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style scoped>
</style>
