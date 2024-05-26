<template>
    <div class="nested-component-1">
      <h2>Nested Component 1</h2>
      <button @click="sendDataToParent">Kirim Data ke Parent</button>
      <slot name="extra"></slot>
      <NestedComponent2 @sendNestedData="handleNestedData"></NestedComponent2>
    </div>
  </template>
  
  <script>
  import NestedComponent2 from './NestedComponent2.vue';
  
  export default {
    components: {
      NestedComponent2
    },
    methods: {
      sendDataToParent() {
        this.$emit('sendData', 'Data dari NestedComponent1');
      },
      handleNestedData(data) {
        this.$emit('sendData', data);
      }
    }
  };
  </script>
  
  <style scoped>
  .nested-component-1 {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px;
  }
  </style>
  