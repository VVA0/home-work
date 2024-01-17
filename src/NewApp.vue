<template>
  <div class="page">
    <Header />
    <!-- <div>
      <router-link :to="{ name: 'contact' }">Перейти к contact</router-link>
      <router-link :to="{ name: 'login' }">Перейти к login</router-link>   !!!!----- ЭТОТ ЗАКОМЕНТИРОВАННЫЙ КОД Я ПЕРЕНЕСЛА В компонент header
      <router-link :to="{ name: 'list' }">Перейти к list</router-link>
      <router-link
        :to="{
          name: 'registr',
          query: {
            user: 'vika',
            test: 1,
          },
        }"
        >Перейти к registr</router-link
      >
      <span @click="goToContact">Contact function</span>
    </div> -->
    <div class="page__body">
      <router-view></router-view>
      <!-- <div><LoginForm /></div>
    <div><ContactForm /></div>
    <div><RegistrForm /></div>
    <div><ListItems /></div> -->
    </div>
    <Footer />
  </div>
</template>

<script>
import ContactForm from "./components/ContactForm/Index.vue";
import LoginForm from "./components/LoginForm/Index.vue";
import RegistrForm from "./components/RegistrForm/Index.vue";
import ListItems from "./components/ListItems/Index.vue";
import Footer from "./components/Layots/Footer.vue";
import Header from "./components/Layots/Header.vue";

export default {
  name: "NewApp",
  components: {
    LoginForm,
    ContactForm,
    RegistrForm,
    ListItems,
    Footer,
    Header,
  },
  methods: {
    goToContact() {
      this.$router.push({ name: "contact" });
    },
  },
};
</script>

<style scoped lang="scss">
.page {
  display: flex;
  flex-direction: column;
  height: 100vh;
  &__body {
    flex: 1;
  }
}
</style>
