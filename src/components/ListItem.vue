<template>
  <ul>
    <li v-for="(item, itemIndex) in itemProp" :key="itemIndex">
      {{ item }}
      <button @click="deleteItem">Delete</button>
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
