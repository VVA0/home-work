<template>
  <button @click="logButton">{{ title }}</button>
</template>

<script>
export default {
  name: "LoginButton",
  props: ["button", "title"],
  methods: {
    logButton() {
      this.$emit("pressButton");
    },
  },
};
</script>

<style></style>
