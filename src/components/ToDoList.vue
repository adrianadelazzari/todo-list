<template>
  <div>
    <div>Add a todo:</div>
    <input type="text" v-model="value" />
    <button @click="addToDo">Add</button>
  </div>
  <div>
    <div>My todo list:</div>
    <ul>
      <li v-for="(item, itemIndex) in toDoList" :key="itemIndex">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      toDoList: [],
      value: undefined,
    };
  },
  methods: {
    addToDo() {
      this.toDoList.push(this.value);
      this.value = undefined;
    },
  },
};
</script>
