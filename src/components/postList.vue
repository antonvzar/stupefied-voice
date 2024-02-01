<template>
  <div v-if="posts.length > 0">
    <h3>Users list</h3>
    <post-item
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
    />
  </div>
  <h2 v-else style="color: red">There's no posts at all</h2>
</template>

<script>
import postItem from "@/components/postItem";
export default {
  components: { postItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped></style>
