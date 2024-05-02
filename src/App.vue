<template>
  <div class="background">
    <img src="https://wallpapercave.com/wp/wp2866857.jpg" />
  </div>
  <div id="app">
    <h1>Sign Up</h1>
    <form>
      <div>
        <label for="username">Username:</label>
        <input type="text" id="username" v-model="username" required>
      </div>
      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" required>
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <div>
        <button @click="handleSubmit">Sign Up</button>
        <p v-if="showSuccess" class="success-message">Sukses Sign-up</p>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const username = ref('');
const email = ref('');
const password = ref('');
const showSuccess = ref('');

const handleSubmit = () => {
  console.log('Form submitted:', { username: username.value, email: email.value, password: password.value });
  showSuccess.value = true;
};




</script>

<style scoped>
#app {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  background-size: cover;
  background-position: center;
}

h1 {
  text-align: center;
  margin-bottom: 20px;
  color: #333;
}

form {
  display: grid;
  gap: 15px;
}

label {
  font-weight: bold;
}

input {
  width: 80%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  width: 100%;
  padding: 10px;
  border: none;
  border-radius: 5px;
  background-color: #007bff;
  color: #fff;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

button:active {
  background-color: #004999;
}

button:focus {
  outline: none;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

.background img {
  position: fixed;
  top: 0;
  left: 0;
  min-height: 90%;
  min-width: 1500px;
  width: 100%;
  height: 100%;
  overflow: hidden;
  z-index: -2;
  object-fit: cover;
  -webkit-background-size:cover; -moz-background-size:cover; -o-background-size:cover; background-size: cover;
  filter: brightness(0.8);
}

.success-message {
  text-align: center;
  margin-top: 20px;
  color: green;
}
</style>
