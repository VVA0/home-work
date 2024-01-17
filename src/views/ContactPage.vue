<template>
  <div class="contact-page">
    <h2 class="contact-page__title">Contact page</h2>
    <p>User id: {{ id }}</p>
    <ContactForm />
  </div>
</template>

<script>
import ContactForm from "../components/ContactForm/Index.vue";

export default {
  name: "ContactPage",
  components: {
    ContactForm,
  },
  data() {
    return {
      id: null,
    };
  },
  //   props: ["id"],
  mounted() {
    this.id = this.$route.params.id;
    console.log(this.$route.params);
  },
};
</script>

<style scoped lang="scss">
.contact-page {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 40px 0;
  &__title {
    padding-bottom: 20px;
  }
}
</style>
