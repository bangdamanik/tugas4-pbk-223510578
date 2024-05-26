<template>
    <div class="nested-component-2">
      <h3>Nested Component 2</h3>
      <button @click="sendNestedDataToParent">Kirim Data dari NestedComponent2</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      sendNestedDataToParent() {
        this.$emit('sendNestedData', 'Data dari NestedComponent2');
      }
    }
  };
  </script>
  
  <style scoped>
  .nested-component-2 {
    background-color: #f9f9f9;
    padding: 10px;
    border-radius: 5px;
  }
  </style>
  