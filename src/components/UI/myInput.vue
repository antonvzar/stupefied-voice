<template>
  <input :value="modelValue" @input="updateInput" class="input" type="text" />
</template>

<script>
export default {
  name: "my-input",
  props: { modelValue: [String, Number] },
  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<style scoped>
.input {
  display: flex;
  border-radius: 5px;
  padding: 3px;
  margin-top: 8px;
  width: 100%;
  border: 2px solid darkblue;
}
</style>
