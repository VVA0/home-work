<template>
  <div>
    <input @input="inputName" :value="nameProps" placeholder="Введите имя" />
  </div>
</template>

<script>
export default {
  name: "NameInput",
  props: ["nameProps"],
  methods: {
    inputName(value) {
      this.$emit("sendName", value.target.value);
    },
  },
};
</script>

<style></style>
