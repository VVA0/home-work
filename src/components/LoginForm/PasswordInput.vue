<template>
  <input
    @input="inputPassword"
    :value="password"
    placeholder="Введите пароль"
  />
</template>

<script>
export default {
  name: "PasswordInput",
  props: ["password"],
  methods: {
    inputPassword(value) {
      this.$emit("sendPassword", value.target.value);
    },
  },
};
</script>

<style></style>
