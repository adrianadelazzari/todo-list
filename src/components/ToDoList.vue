<template>
  <div>
    <div>Add a todo:</div>
    <input type="text" v-model="value" />
    <button @click="addToDo">Add</button>
  </div>
  <div>
    <div>My todo list:</div>
    <ListItem :itemProp="toDoListArr" @deleteItem="removeToDo" />
  </div>
  <button @click="removeAll">Delete All</button>
</template>

<script>
import ListItem from "./ListItem.vue";

export default {
  components: {
    ListItem,
  },
  data() {
    return {
      toDoListArr: [],
      value: undefined,
    };
  },
  methods: {
    addToDo() {
      this.toDoListArr.push(this.value);
      this.value = undefined;
    },
    removeToDo(itemProp){
      this.toDoListArr.splice(this.toDoListArr.indexOf(itemProp), 1)
    },
    removeAll() {
      this.toDoListArr = [];
    },
  },
};
</script>
