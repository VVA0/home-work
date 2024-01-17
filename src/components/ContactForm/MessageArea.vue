<template>
  <div>
    <textarea
      @input="inputMessage"
      :value="message"
      placeholder="Введите сообщение"
    />
  </div>
</template>

<script>
export default {
  name: "MessageArea",
  props: ["message"],
  methods: {
    inputMessage(value) {
      this.$emit("sendMessage", value.target.value);
    },
  },
};
</script>

<style></style>
