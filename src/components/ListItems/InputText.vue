<template>
  <div>
    <input v-model="textComputed" />
  </div>
</template>

<script>
export default {
  name: "InputText",
  props: ["text"],
  computed: {
    textComputed: {
      get() {
        return this.text;
      },
      set(value) {
        this.$emit("input", value);
      },
    },
  },
};
</script>

<style></style>
