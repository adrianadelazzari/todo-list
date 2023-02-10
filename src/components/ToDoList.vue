<template>
  <div>
    <div>Add a todo:</div>
    <input type="text" v-model="value" />
    <button @click="addToDo">Add</button>
  </div>
  <div>
    <div>My todo list:</div>
    <ListItem :itemProp="toDoListArr" />
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
  },
};
</script>
