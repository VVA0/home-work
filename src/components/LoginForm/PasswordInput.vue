<template>
  <input
    v-model="passwordComputed"
    :class="{ error: hasError }"
    placeholder="Введите пароль"
  />
</template>

<script>
export default {
  name: "PasswordInput",
  props: ["password"],
  computed: {
    hasError() {
      return this.passwordComputed.length < 10;
    },
    passwordComputed: {
      get() {
        return this.password;
      },
      set(value) {
        this.$emit("sendPassword", value);
      },
    },
  },
};
</script>

<style scoped>
/*scoped- это (атрибут) для того, чтобы стили применялись только к этому компоненту */
input.error {
  background-color: red;
}
</style>
