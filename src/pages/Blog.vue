<template>
  <div class="blog">
    <h1>Blog Posts</h1>
    <form @submit.prevent="isEditing ? updatePost() : addPost()">
      <input v-model="currentPost.title" placeholder="Title" required />
      <textarea v-model="currentPost.content" placeholder="Content" required></textarea>
      <button type="submit">{{ isEditing ? 'Update' : 'Add' }} Post</button>
    </form>
    <ul>
      <li v-for="post in posts" :key="post.id">
        <h3>{{ post.title }}</h3>
        <p>{{ post.content }}</p>
        <button @click="editPost(post)">Edit</button>
        <button @click="deletePost(post.id)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Blog',
  data() {
    return {
      posts: [],
      currentPost: { id: null, title: '', content: '' },
      isEditing: false,
    };
  },
  methods: {
    addPost() {
      const newPost = { ...this.currentPost, id: Date.now() };
      this.posts.push(newPost);
      this.resetForm();
    },
    editPost(post) {
      this.currentPost = { ...post };
      this.isEditing = true;
    },
    updatePost() {
      const index = this.posts.findIndex(post => post.id === this.currentPost.id);
      if (index !== -1) {
        this.posts.splice(index, 1, { ...this.currentPost });
        this.resetForm();
      }
    },
    deletePost(id) {
      this.posts = this.posts.filter(post => post.id !== id);
    },
    resetForm() {
      this.currentPost = { id: null, title: '', content: '' };
      this.isEditing = false;
    },
  },
};
</script>

<style scoped>
.blog {
  max-width: 1500px;
  margin: 0 auto;
  padding: 20px;
  background-color: #007bff;
}
form {
  margin-bottom: 20px;
}
input,
textarea {
  width: 100%;
  margin-bottom: 10px;
  padding: 8px;
  box-sizing: border-box;
}
button {
  margin-right: 10px;

}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin-bottom: 20px;
}
</style>
