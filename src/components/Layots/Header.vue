<template>
  <header class="header">
    <router-link
      :style="{ color: linkColor }"
      class="header__link"
      :to="{
        name: 'contact',
        params: {
          id: 123,
        },
      }"
      >Перейти к contact</router-link
    >
    <router-link class="header__link" :to="{ name: 'login' }"
      >Перейти к login</router-link
    >
    <router-link class="header__link" :to="{ name: 'list' }"
      >Перейти к list</router-link
    >
    <router-link
      class="header__link"
      :to="{
        name: 'registr',
        query: {
          user: 'vika',
          test: 1,
        },
      }"
      >Перейти к registr</router-link
    >
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      linkColor: "black",
    };
  },
};
</script>

<style scoped lang="scss">
.header {
  display: flex;
  justify-content: center;
  &__link {
    padding: 0px 10px;
  }
}
</style>
