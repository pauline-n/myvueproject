<template>
    <nav class="navbar">
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#blog">Blog</a></li>
        <li><a href="#about">About Fashion</a></li>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Navbar',
  };
  </script>
  
  <style scoped>
  .navbar {
    background-color: #333;
    color: white;
    padding: 10px 20px;
  }
  
  .navbar ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
  }
  
  .navbar li {
    margin-right: 20px;
  }
  
  .navbar a {
    color: white;
    text-decoration: none;
  }
  
  .navbar a:hover {
    text-decoration: underline;
  }
  </style>
  