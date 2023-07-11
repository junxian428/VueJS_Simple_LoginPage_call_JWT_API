<template>
  <div>
    <h1>Login</h1>
    <form @submit.prevent="login">
      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" required>
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <div>
        <button type="submit">Login</button>
      </div>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    login() {
      const loginData = {
        email: this.email,
        password: this.password
      };

      axios.post('http://localhost:8086/api/v1/auth/authenticate', loginData)
        .then(response => {
          // Handle successful login
          console.log(response.data);
          // Redirect user to another page if needed
             // Redirect user to another page
          this.$router.push('/dashboard'); // Replace '/dashboard' with your desired route
        })
        .catch(error => {
          // Handle login error
          console.error(error);
        });
    }
  }
};
</script>
