<!-- Child component -->
<template>
  <div class="child">
    <h3>Child Component</h3>
    <button @click="sendDataToParent">Send Data to Parent</button>
    <p>Data from Parent: {{ dataFromParent }}</p>
  </div>
</template>

<script>
export default {
  props: {
    dataFromParent: Object,
  },
  methods: {
    sendDataToParent() {
  
      const jsonData = { name: 'Alice', age: 30 };
      this.$emit('sendDataToParent', jsonData);
    },
  },
};

</script>

<style>
.child {
  margin: 50px;
  border: 1px solid black;
  padding: 20px;
}
</style>
