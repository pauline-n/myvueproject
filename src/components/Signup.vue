// eslint-disable-next-line vue/multi-word-component-names
<template>
    <div class="modal">
      <h2>Sign Up</h2>
      <form @submit.prevent="submitForm">
        <input type="text" placeholder="Username" v-model="username" required />
        <input type="email" placeholder="Email" v-model="email" required />
        <input type="password" placeholder="Password" v-model="password" required />
        <button type="submit">Sign Up</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        username: '',
        email: '',
        password: '',
      };
    },
    methods: {
      submitForm() {
        alert(`User ${this.username} signed up!`);
      },
    },
  };
  </script>
  
  <style>
  .modal {
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 10px;
    width: 300px;
  }
  </style>
  