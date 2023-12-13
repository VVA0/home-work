<template>
  <div>
    <EmailInput :email="email" @sendEmail="setEmail" />
    <PasswordInput :password="password" @sendPassword="setPassword" />
    <LoginButton @pressButton="login" title="save" />
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
      email: "",
      password: "",
      button: "Login",
    };
  },
  methods: {
    setEmail(value) {
      this.email = value;
    },
    setPassword(value) {
      this.password = value;
    },
    login() {
      console.log({
        email: this.email,
        password: this.password,
      });
    },
  },
};
</script>

<style></style>
