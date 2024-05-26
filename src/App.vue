<template>
  <div id="app">
    <h1>Joner Okto Sanjogi Damanik</h1>
    <NestedComponent1 @sendData="handleData">
      <template v-slot:extra>
        <p class="extra-content">Data dari App ke Slot NestedComponent1</p>
      </template>
    </NestedComponent1>
    <p>Data dari Child: {{ receivedData }}</p>
  </div>
</template>

<script>
import NestedComponent1 from './components/NestedComponent1.vue';

export default {
  components: {
    NestedComponent1
  },
  data() {
    return {
      receivedData: ''
    };
  },
  methods: {
    handleData(data) {
      this.receivedData = data;
    }
  }
};
</script>

<style scoped>
#app {
  text-align: center;
  font-family: Arial, sans-serif;
}

.extra-content {
  color: blue;
  font-weight: bold;
}
</style>
