<template>
  <div id="app">
    <o-input placeholder="test" :value="name" @input-test="setName" />
    <o-input v-model="name" />
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
import OInput from "./components/UI/OInput.vue"; /*Тут я импортирую новый компонент */
export default {
  name: "App",
  components: {
    OInput,
  },
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
    setName(value) {
      this.name = value;
    } /* метод который меняет значение name*/,
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
