<template>
  <input v-model="emailComputed" placeholder="Введите email" />
</template>

<script>
export default {
  name: "EmailInput",
  props: ["email"],
  computed: {
    emailComputed: {
      get() {
        return this.email;
      },
      set(value) {
        this.$emit("sendEmail", value);
      },
    },
  },
};
</script>

<style></style>
