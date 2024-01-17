<template>
  <div>
    <NameInput @sendName="setName" :nameProps="name" />
    <EmailInput @sendEmail="setEmailInput" :emailProps="email" />
    <Password @sendPassword="setPassword" :passwordProps="password" />
    <ConfirmPassword
      @sendPasswordConfirm="setConfirmPassword"
      :passwordConfirmProps="passwordConfirm"
    />
    <SendButton @pressButton="registr" :textProps="textButton" />
  </div>
</template>

<script>
import NameInput from "./NameInput.vue";
import EmailInput from "./EmailInput.vue";
import Password from "./Password.vue";
import ConfirmPassword from "./ConfirmPassword.vue";
import SendButton from "./SendButton.vue";

export default {
  name: "RegistrForm",
  components: {
    NameInput,
    EmailInput,
    Password,
    ConfirmPassword,
    SendButton,
  },
  data() {
    return {
      // name: "",
      // email: "",
      password: "",
      passwordConfirm: "",
      textButton: "Регистрация",
    };
  },
  computed: {
    email: {
      get() {
        return this.$route.query.email;
      },
      set(value) {
        this.$router.replace({
          name: "registr",
          query: {
            ...this.$route.query,
            email: value,
          },
        });
      },
    },
    name: {
      get() {
        return this.$route.query.name;
      },
      set(value) {
        this.$router.replace({
          name: "registr",
          query: {
            ...this.$route.query,
            name: value,
          },
        });
      },
    },
  },
  mounted() {
    console.log(this.$route.query);
  },
  methods: {
    setName(value) {
      this.name = value;
    },
    setEmailInput(value) {
      this.email = value;
    },
    setPassword(value) {
      this.password = value;
    },
    setConfirmPassword(value) {
      this.passwordConfirm = value;
    },
    registr() {
      console.log(this.name, this.email, this.password, this.passwordConfirm);
    },
  },
};
</script>
