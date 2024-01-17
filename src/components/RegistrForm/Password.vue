<template>
  <div>
    <input
      @input="inputPassword"
      :value="passwordProps"
      placeholder="Введите пароль"
    />
  </div>
</template>

<script>
export default {
  name: "Password",
  props: ["passwordProps"],
  methods: {
    inputPassword(value) {
      this.$emit("sendPassword", value.target.value);
    },
  },
};
</script>

<style></style>
