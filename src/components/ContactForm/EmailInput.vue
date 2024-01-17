<template>
  <div>
    <input @input="inputEmail" :value="email" placeholder="Введите email" />
  </div>
</template>

<script>
export default {
  name: "EmailInput",
  props: ["email"],
  methods: {
    inputEmail(value) {
      this.$emit("sendEmail", value.target.value);
    },
  },
};
</script>

<style></style>
