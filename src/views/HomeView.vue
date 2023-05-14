<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostListView :posts="posts" />
    </div>
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import PostListView from "../components/PostListView";
import getPosts from "../composables/getPosts";

export default {
  name: "HomeView",
  components: { PostListView },
  setup() {
    const { posts, error, load } = getPosts();
    load();
    return { posts, error };
  },
};
</script>
