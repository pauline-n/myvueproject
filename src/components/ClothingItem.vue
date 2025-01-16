<template>
    <div class="clothing-item">
      <h2>{{ name }}</h2>
      <p>{{ description }}</p>
      <p><strong>{{ price }}</strong></p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['name', 'price', 'description'],
  };
  </script>
  
  <style scoped>
  .clothing-item {
    border: 1px solid #ddd;
    padding: 15px;
    margin: 10px;
  }
  </style>
  