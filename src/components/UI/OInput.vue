<template>
  <input
    @input="setInput($event.target.value)"
    :placeholder="placeholder"
    :value="value || valueModel"
  />
</template>

<script>
/*Скрипт обязательно*/
export default {
  name: "OInput",
  model: {
    prop: "valueModel" /*это название из props (по дефолту назвается value)*/,
    event: "update" /*это название $emit (по дефолту называет input)*/,
  },
  props: [
    "value",
    "placeholder",
    "valueModel",
  ] /* Пропсы с которыми я работаю выше в этом же файле*/,
  methods: {
    setInput(inputValue) {
      /*Функция которая принимает введенное значение*/
      this.$emit(
        "input-test",
        inputValue
      ); /*emit- это функция(название которое я даю, то что передаем - параметры ) */
      this.$emit("input", inputValue); /*первый вариант работы*/
      this.$emit("update", inputValue); /*второй вариант*/
    },
  },
};
</script>

<style></style>
