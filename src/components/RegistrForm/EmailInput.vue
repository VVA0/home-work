<template>
  <div>
    <input
      @input="inputEmail"
      :value="emailProps"
      placeholder="Введите email"
    />
  </div>
</template>

<script>
export default {
  name: "EmailInput",
  props: ["emailProps"],
  methods: {
    inputEmail(value) {
      this.$emit("sendEmail", value.target.value);
    },
  },
};
</script>

<style></style>
