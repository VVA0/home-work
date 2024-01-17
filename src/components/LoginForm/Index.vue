<template>
  <div>
    <EmailInput :email="email" @sendEmail="setEmail" />
    <PasswordInput :password="password" @sendPassword="setPassword" />
    <LoginButton @pressButton="login" title="save" />
    {{ dataForm }}
  </div>
</template>

<script>
import EmailInput from "./EmailInput.vue";
import PasswordInput from "./PasswordInput.vue";
import LoginButton from "./LoginButton.vue";
export default {
  name: "LoginForm",
  components: {
    EmailInput,
    PasswordInput,
    LoginButton,
  },
  data() {
    return {
      // email: "",
      password: "",
      button: "Login",
    };
  },

  computed: {
    dataForm() {
      console.log("hello!");
      return this.email + " " + this.password;
    },
    email: {
      get() {
        return this.$route.query.email;
      },
      set(value) {
        this.$router.replace({
          name: "login",
          query: {
            ...this.$route.query,
            email: value,
          },
        });
      },
    },
  },

  methods: {
    setEmail(value) {
      this.email = value;
    },
    setPassword(value) {
      this.password = value;
    },
    login() {
      console.log(this.dataForm);
    },
  },
};
</script>

<style></style>
