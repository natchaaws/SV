<template>
  <div>
    <b-container class="bv-example-row">
    <b-row class="text-center">
         <b-col></b-col>

         <b-col cols="10" class="bg4">

    <h1>User Login</h1><hr>
    <form v-on:submit.prevent="onLogin">
      <p>Username : <input type="text" v-model="email"></p>
      <p>Password : <input type="password" v-model="password"></p>

      <p><b-button variant="success" type="submit">Login</b-button></p>
      <div class="error" v-if="error">{{error}}</div>
    </form>

    </b-col>
      <b-col> </b-col>
     </b-row>
</b-container>

  </div>
</template>

<script>

import AuthenService from '@/services/AuthenService'

export default {
  data () {
    return {
      email: '',
      password: '',
      error: null 
    }
  },

  methods: {
    async onLogin(){
      try {
        const response = await AuthenService.login({
          email: this.email,
          password: this.password
        })
      
        this.$store.dispatch('setToken', response.data.token)
        this.$store.dispatch('setUser', response.data.user)

        this.$router.push({
          name: 'users'
        })
       

      } catch(error) {
        console.log(error)
        this.error = error.response.data.error //แสดง error ถ้าใส่รหัสผิด หรือรหัสไม่มีอยู่ในฐานข้อมูล
        this.email = ''
        this.password = ''
      }
    }
  },
}
</script>
<style scoped>
  .error {
    color:red;
  }
</style>