<template>
  <div>
    <EmailInput @sendEmail="setEmail" :email="email" />
    <MessageArea @sendMessage="setMessage" :message="message" />
    <SendButton @click="showData" :textButton="button" />
  </div>
</template>

<script>
import EmailInput from "./EmailInput.vue";
import MessageArea from "./MessageArea.vue";
import SendButton from "./SendButton.vue";

export default {
  name: "ContactForm",
  components: {
    EmailInput,
    MessageArea,
    SendButton,
  },
  data() {
    return {
      email: "",
      message: "",
      button: "send",
    };
  },
  methods: {
    setEmail(value) {
      this.email = value;
    },
    setMessage(value) {
      this.message = value;
    },
    showData() {
      // console.log(this.email, this.message);
      this.setEmail("Hello!");
    },
  },
};
</script>

<style></style>
