<template>
  <ul>
    <li v-for="(item, itemIndex) in itemProp" :key="itemIndex">
      {{ item }}
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
};
</script>
