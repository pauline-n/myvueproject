<template>
    <button class="custom-button" @click="onClick">
      <slot></slot>
    </button>
  </template>
  
  <script>
  export default {
    name: 'CustomButton',
    methods: {
      onClick() {
        this.$emit('click');
      },
    },
  };
  </script>
  
  <style scoped>
.custom-button {
  margin-right: 10px; 
  background-color: #007bff;
  color: white;
  border: none;
  padding: 20px 25px;
  border-radius: 5px;
  cursor: pointer;
}

.custom-button:hover {
  background-color: #0056b3;
}
</style>

  