<template>
  <div>
    <button @click="clickButton">{{ textProps }}</button>
  </div>
</template>

<script>
export default {
  name: "SendButton",
  props: ["textProps"],
  methods: {
    clickButton() {
      this.$emit("pressButton");
    },
  },
};
</script>

<style></style>
