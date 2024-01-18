<!-- Parent component -->
<template>
  <div class="parent">
    <h2>Parent Component</h2>
    <button @click="sendDataToChild">Send Data to Child</button>
    <p>Name: {{ dataFromChild ? dataFromChild.name : '' }}</p>
    <p>Age: {{ dataFromChild ? dataFromChild.age : '' }}</p>

    <Child :parentData="parentData" @sendDataToParent="receiveDataFromChild" ref="child" />
  </div>
</template>

<script>
import Child from './Child.vue';

export default {
  components: {
    Child,
  },
  data() {
    return {
      parentData: {
        name: 'John',
        age: 25,
      },
      dataFromChild: null,
    };
  },
  methods: {
    sendDataToChild() {
      const jsonData = { name: 'John', age: 25 };
      this.$refs.child.sendDataToParent(jsonData);
    },
    receiveDataFromChild(data) {
      this.dataFromChild = data;
    },
  },
};
</script>

<style>
.parent {
  margin: 50px;
  border: 1px solid black;
  padding: 20px;
}
</style>
