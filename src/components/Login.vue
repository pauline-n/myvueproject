<template>
    <div class="modal">
      <h2>Log In</h2>
      <form @submit.prevent="submitForm">
        <input type="email" placeholder="Email" v-model="email" required />
        <input type="password" placeholder="Password" v-model="password" required />
        <button type="submit">Log In</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        email: '',
        password: '',
      };
    },
    methods: {
      submitForm() {
        alert(`User with email ${this.email} logged in!`);
      },
    },
  };
  </script>
  
  <style scoped>
  .modal {
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 10px;
    width: 300px;
  }
  </style>
  