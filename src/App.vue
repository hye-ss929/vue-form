<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id: </label>
      <input type="text" id="username" v-model="username">
    </div>
    <div>
      <label for="password">pw: </label>
      <input type="password" id="password" v-model="password">
    </div>
    <button type="submit" >Login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data:function () {
    return {
      username:"",
      password:"",
    }
  },
  methods:{
    submitForm:function () {
      const url = "https://jsonplaceholder.typicode.com/users"
      const data = {
        username: this.username,
        password: this.password
      }
      axios.post(url, data) //
          .then(res => console.log(res)) //
          .catch(err => console.log(err))
    }
  }
}
</script>

<style>

</style>
