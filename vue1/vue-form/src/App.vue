<template>
  <!-- submit.prevent 는 form 의 새로고침을 막아준다 -->
  <form action="" v-on:submit.prevent="submitLogin"> 
    <div>
      <label for="username">id: </label>
      <input id="username" type="text" v-model="username"> {{usernameLength}}/50
    </div>

    <div>
      <label for="password">pw: </label>
      <input id="password" type="password" v-model="password"> {{passwordLength}}/50
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data: function() {
    return {
      username: '',
      password: ''
    }
  },
  computed: {
    usernameLength: function() {
      return this.username.length;
    },
    passwordLength: function() {
      return this.password.length;
    }
  },
  methods: {
    submitLogin: function() {
      // event.preventDefault()  // form 의 새로고침을 막아줌
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users'

      var data = {
        username: this.username,
        password: this.password
      }

      axios.post(url, data)
          .then(function(response) {
            console.log(response);
          })
          .catch(function(error) {
            console.log(error);
          });
    }
  }
}
</script>

<style>

</style>