<template>
    <div>
      <div>Add a todo:</div>
      <input type="text" v-model="value"/>
      <p>{{ value }}</p>
    </div>
  </template>
  
  <script>
  export default{
    data(){
      return{
        value: undefined
      }
    }
  }
  </script>