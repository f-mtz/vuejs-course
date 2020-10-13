<template>
  <div id="app">
    <h1>Vue JS</h1>
    <Post>
      <h1>Components no Vue</h1>
      <p>Components são muito importantes</p>
    </Post>

  </div>
</template>

<script>

import Post from './components/Post.vue'
export default {
  components: {
    Post
  }
}
</script>
