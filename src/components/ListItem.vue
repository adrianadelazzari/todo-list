<template>
  <ul>
    <li v-for="(item, itemIndex) in itemProp" :key="itemIndex">
      {{ item }}
      <button class="deleteItemBtn" @click="deleteItem">Delete</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    itemProp: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    deleteItem() {
      this.$emit("deleteItem", this.item);
    },
  },
};
</script>

<style>
ul li {
  position: relative;
  padding: 12px 8px 12px 40px;
  font-size: 18px;
  transition: 0.2s;
  list-style-type: none
}
.deleteItemBtn {
  padding: 2px;
  width: 7%;
  background: red;
  color: white;
  text-align: center;
  font-size: 15px;
  cursor: pointer;
  transition: 0.3s;
  border-radius: 0;
}
</style>
