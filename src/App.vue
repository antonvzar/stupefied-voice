<template>
  <div class="app">
    <h1>Page with posts</h1>
    <my-button @click="showDialogue" style="margin: 15px 0"
      >Create the post</my-button
    >
    <my-dialogue v-model:show="dialogueVisible">
      <post-form @create="createPost" />
    </my-dialogue>

    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import postForm from "@/components/postForm";
import postList from "@/components/postList";
import myDialogue from "@/components/UI/myDialogue";
export default {
  components: {
    postList,
    postForm,
    myDialogue,
  },
  data() {
    return {
      posts: [
        { id: "1", title: "JS 1", body: "Post Description" },
        { id: "2", title: "JS 2", body: "Post Description" },
        { id: "3", title: "JS 3", body: "Post Description" },
      ],
      dialogueVisible: false,
      modificatorValue: "",
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogueVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id);
    },
    showDialogue() {
      this.dialogueVisible = true;
    },
    async fetchPosts() {},
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
