<template>
  <div class="post">
    <div class="post__info">
      <div>
        <strong>Name: </strong>
        {{ post.title }}
      </div>
      <div>
        <strong>Description: </strong>
        {{ post.body }}
      </div>
    </div>
    <div>
      <my-button @click="$emit('remove', post)">Delete post</my-button>
    </div>
  </div>
</template>

<script>
import myButton from "@/components/UI/myButton";
export default {
  components: {
    myButton,
  },
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid teal;
  border-radius: 3px;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.post__btn {
  display: flex;
  padding: 7px;
  border: 2px solid #1faee9;
  border-radius: 5px;
}
</style>
