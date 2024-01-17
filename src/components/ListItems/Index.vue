<template>
  <div>
    <InputText @input="setInputText" :text="inputText" />
    <button @click="addItem">Добавить</button>
    <button @click="removeItem">Удалить</button>
    <button @click="showList">Показать/Спрятать</button>

    <ul v-show="isShownList">
      <ListItem
        v-for="(item, index) in filteredList"
        :index="index"
        :item="item"
        :key="index"
      />
      <!-- <li v-for="(item, index) in filteredList" :key="index">
        {{ index }} {{ item }}
      </li> -->
    </ul>
  </div>
</template>

<script>
import InputText from "./InputText.vue";
import ListItem from "./ListItem.vue";

export default {
  name: "ListItems",
  components: {
    InputText,
    ListItem,
  },
  data() {
    return {
      list: ["fanta"],
      inputText: "",
      isShownList: true,
    };
  },
  computed: {
    filteredList() {
      console.log(this.list);
      return this.list;
    },
  },
  methods: {
    setInputText(value) {
      this.inputText = value;
    },
    addItem() {
      this.list.push(this.inputText);
      this.inputText = "";
    },
    removeItem() {
      this.list.pop();
    },
    showList() {
      this.isShownList = !this.isShownList;
    },
  },
};
</script>

<style></style>
