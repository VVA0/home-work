<template>
  <div>
    <button @click="clickButton">{{ textButton }}</button>
  </div>
</template>

<script>
export default {
  name: "SendButton",
  props: ["textButton"],
  methods: {
    clickButton() {
      this.$emit("click");
    },
  },
};
</script>

<style></style>
