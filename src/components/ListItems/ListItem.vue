<template>
  <li ref="item">{{ index }} {{ item }}!!</li>
</template>

<script>
export default {
  name: "ListItem",
  props: ["index", "item"],
  created() {
    console.log("created");
    console.log(this.index);
    console.log(this.$refs.item);
  },
  mounted() {
    console.log("mounted");
    console.log(this.index);
    console.log(this.$refs.item);
  },
  destroyed() {
    console.log("destroyed");
    console.log(this.index);
    console.log(this.$refs.item);
  },
  beforeCreate() {
    console.log("beforeCreate");
    console.log(this.index);
    console.log(this.$refs);
  },
  beforeMount() {
    console.log("beforeMount");
    console.log(this.index);
    console.log(this.$refs);
  },
  beforeDestroy() {
    console.log("beforeDestroy");
    console.log(this.index);
    console.log(this.$refs);
  },
};
</script>

<style></style>
