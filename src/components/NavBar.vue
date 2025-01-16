<template>
    <nav class="navbar">
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/blog">Blog</router-link></li>
        <li><router-link to="/about">About Fashion</router-link></li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'NavBar',
  };
  </script>
  
  <style>
  .navbar {
    background: #333;
    padding: 10px;
  }
  .navbar ul {
    display: flex;
    list-style: none;
  }
  .navbar li {
    margin-right: 15px;
  }
  .navbar a {
    color: white;
    text-decoration: none;
  }
  </style>
  