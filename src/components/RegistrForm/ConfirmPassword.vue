<template>
  <div>
    <input
      @input="inputPasswordConfirm"
      :value="passwordConfirmProps"
      placeholder="Повторите пароль"
    />
  </div>
</template>

<script>
export default {
  name: "ConfirmPassword",
  props: ["passwordConfirmProps"],
  methods: {
    inputPasswordConfirm(value) {
      this.$emit("sendPasswordConfirm", value.target.value);
    },
  },
};
</script>

<style></style>
