<template>
  <div id="app">
    <NavBar />
    <h1>Men's Clothing Store</h1>
    <clothing-item
      v-for="(item, index) in items"
      :key="index"
      :name="item.name"
      :price="item.price"
      :description="item.description"
    />
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue';
import ClothingItem from './components/ClothingItem.vue';

export default {
  components: {
    NavBar,
    ClothingItem,
  },
  data() {
    return {
      items: [
        { name: 'Casual Shirt', price: 'Shs 25000', description: 'A comfortable cotton shirt.' },
        { name: 'Formal Trousers', price: 'SHs 40000', description: 'Perfect for office wear.' },
        { name: 'Leather Jacket', price: 'Shs 100000', description: 'Stylish and warm.' }
      ],
    };
  },
};
</script>

<style>
#app {
  text-align: center;
  font-family: Arial, sans-serif;
}
</style>

