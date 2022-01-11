<template>
  <div>
    <form v-on:submit.prevent="submitForm">
      <div>
        <label for="username">ID: </label>
        <input id="username" type="text" v-model="username" />
      </div>
      <div>
        <label for="password">PW: </label>
        <input id="password" type="text" v-model="password" />
      </div>
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data: function () {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    submitForm: function () {
      console.log(this.username, this.password);
      const url = 'https://jsonplaceholder.typicode.com/users';
      const body = {
        username: this.username,
        password: this.password,
      };
      axios
        .post(url, body)
        .then(function (response) {
          console.log(response);
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
};
</script>

<style></style>
