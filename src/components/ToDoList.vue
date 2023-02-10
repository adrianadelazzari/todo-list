<template>
  <div class="container">
    <div class="header">Add a todo:</div>
    <input type="text" v-model="value" />
    <button class="addBtn" @click="addToDo">Add</button>
    <div class="header">My todo list:</div>
    <ListItem :itemProp="toDoListArr" @deleteItem="removeToDo" />
    <button class="deleteAllBtn" @click="removeAll">Delete All</button>
  </div>
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
    removeToDo(itemProp) {
      this.toDoListArr.splice(this.toDoListArr.indexOf(itemProp), 1);
    },
    removeAll() {
      this.toDoListArr = [];
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
.container {
  padding: 40px;
  text-align: center;
  background-color:hsla(120, 100%, 25%, 0.3)
}
.header {
  padding: 30px;
  text-align: center;
  font-size: large;
  font-weight: bold;
}
input{
  padding: 10px;
  width: 25%;
  font-size: 15px;
  transition: 0.3s;
  border-radius: 0;
  background-color: azure;
}
.addBtn {
  padding: 10px;
  width: 5%;
  background: green;
  color: white;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
  border-radius: 0;
}
.deleteAllBtn {
  padding: 10px;
  width: 10%;
  background: red;
  color: white;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
  border-radius: 0;
}
</style>
