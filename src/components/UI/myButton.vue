<template>
  <div>
    <button class="btn"><slot></slot></button>
  </div>
</template>

<script>
export default {
  name: "my-button",
};
</script>

<style scoped>
.btn {
  padding: 10px 15px;
  display: flex;
  border: 2px solid #1faee9;
  border-radius: 5px;
  background: none;
  align-self: flex-end;
}
</style>
