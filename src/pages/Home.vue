<template>
  <div>
    <!-- <NavBar /> -->
    <h1>Welcome to Men’s Clothing Store</h1>

    <CustomButton @click="showSignup">Sign Up</CustomButton>
    <CustomButton @click="showLogin">Log In</CustomButton>

    <Signup v-if="displaySignup" />
    <Login v-if="displayLogin" />
    
    <img src="/images/barner.jpg" alt="Banner" class="banner-image"/>

     <!-- Product List -->
     <div class="products">
      <div v-for="(item, index) in items" :key="index" class="product">
        <img :src="`/images/products/${item.name.toLowerCase().replace(/\s+/g, '-')}.jpg`" alt="Product Image" class="product-image" />
        <div class="product-details">
          <h3>{{ item.name }}</h3>
          <p>{{ item.description }}</p>
          <p><strong>{{ item.price }}</strong></p>
        </div>
      </div>
    </div>

  </div>
</template>

<script>

import CustomButton from '../components/CustomButton.vue';
import Signup from '../components/Signup.vue';
import Login from '../components/Login.vue';

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Home',
  components: {
    CustomButton,
    Signup,
    Login,
  },
  data() {
    return {
      displaySignup: false,
      displayLogin: false,
      items: [
        { name: 'Casual Shirt', price: 'Ushs 25000', description: 'A comfortable cotton shirt.' },
        { name: 'Formal Trousers', price: 'Ushs 40000', description: 'Perfect for office wear.' },
        { name: 'Leather Jacket', price: 'Ushs 100000', description: 'Stylish and warm.' }
      ],
    };
  },
  methods: {
    showSignup() {
      this.displaySignup = true;
      this.displayLogin = false;
    },
    showLogin() {
      this.displayLogin = true;
      this.displaySignup = false;
    },
  },
};
</script>

<style scoped>
/* Banner Image Styling */
.banner-image {
  width: 100%;
  height: 100vh;
  object-fit: cover;
  display: block;
}

/* Product Grid */
.products {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
  padding: 20px;
}

.product {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.product-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.product-details {
  padding: 15px;
}

.product-details h3 {
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.product-details p {
  font-size: 1rem;
  margin: 5px 0;
}

.product-details strong {
  color: #e67e22;
  font-size: 1.1rem;
}
</style>
