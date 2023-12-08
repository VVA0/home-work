<template>
  <div id="app">
    <input v-model="name" placeholder="name" />
    <input v-model="email" placeholder="email" />
    <input v-model="password" type="password" placeholder="password" />
    <input
      v-model="confirmPassword"
      type="password"
      placeholder="confirm password"
    />
    <button @click="save">Save</button>
    <div v-if="show">
      {{ name }}, {{ email }}, {{ password }}, {{ confirmPassword }}
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "",
      email: "",
      password: "",
      confirmPassword: "",
      show: false,
    };
  },
  computed: {},
  methods: {
    save() {
      this.validPassword();
      this.show = true;
    },
    validPassword() {
      if (this.password === this.confirmPassword) {
        alert("Success");
      } else {
        alert("Error");
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
