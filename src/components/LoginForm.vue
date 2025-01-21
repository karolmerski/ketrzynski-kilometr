<template>
  <div class="login-form">
    <h2>Login</h2>
    <form @submit.prevent="handleSubmit">
      <div>
        <label for="username">Username:</label>
        <input type="text" id="username" v-model="username" required />
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" required />
      </div>
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'LoginForm',
  data() {
    return {
      username: '',
      password: ''
    };
  },
  methods: {
    async handleSubmit() {
      try {
        const response = await axios.post('https://jokaga.dev/ketrzynski-kilometr/api/api.php', {
            action: 'login',
            username: this.username,
            password: this.password
        });
        console.log('Login successful:', response.data);
        // Handle successful login (e.g., redirect to another page)
      } catch (error) {
        console.error('Login failed:', error);
        // Handle login failure (e.g., show error message)
      }
    }
  }
};
</script>

<style scoped>
.login-form {
  max-width: 300px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
.login-form h2 {
  text-align: center;
}
.login-form div {
  margin-bottom: 10px;
}
.login-form label {
  display: block;
  margin-bottom: 5px;
}
.login-form input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}
.login-form button {
  width: 100%;
  padding: 10px;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
.login-form button:hover {
  background-color: #369f6e;
}
</style>
