<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Blog',
  data() {
    return {
      blogPosts: [
        { title: 'Latest Men’s Fashion Trends', content: 'Discover the latest styles and tips for men.' },
        { title: 'How to Style a Leather Jacket', content: 'Explore ideas to style your leather jacket.' },
      ],
    };
  },
};
</script>

<template>
  <div>
    <h1>Fashion Blog</h1>
    <div v-for="(post, index) in blogPosts" :key="index">
      <h2>{{ post.title }}</h2>
      <p>{{ post.content }}</p>
    </div>
  </div>
</template>

<style>
h1 {
  color: #333;
}
</style>
