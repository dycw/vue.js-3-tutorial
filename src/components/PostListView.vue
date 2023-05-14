<template>
  <div class="post-list">
    <div v-for="post in posts" :key="post.id">
      <SinglePostView :post="post" />
    </div>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from "vue";
import SinglePostView from "./SinglePostView";
export default {
  props: ["posts"],
  components: { SinglePostView },
  setup(props) {
    onMounted(() => console.log("component mounted"));
    onUnmounted(() => console.log("component unmounted"));
    onUpdated(() => console.log("component updated"));
  },
};
</script>
