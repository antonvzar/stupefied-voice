<template>
  <form @submit.prevent>
    <h4>Create your post here:</h4>
    <my-input v-model="post.title" type="text" placeholder="Name" />
    <my-input v-model="post.body" type="text" placeholder="Description" />
    <my-button
      style="align-self: flex-end; margin-top: 15px"
      @click="createPost"
      >Submit</my-button
    >
  </form>
</template>

<script>
import myButton from "@/components/UI/myButton";
export default {
  components: {
    myButton,
  },
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
</style>
