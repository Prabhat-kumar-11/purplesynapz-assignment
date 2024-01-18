<!-- ParentComponent.vue -->
<template>
  <div>
    <button @click="sendData">Send Data to Child</button>
    <p>Parent Data: {{ parentData }}</p>
    <ChildComponent :childData="parentData" @childEvent="receiveData"></ChildComponent>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  data() {
    return {
      parentData: { name: 'John', age: 25 }
    };
  },
  methods: {
    sendData() {
      this.$emit('parentEvent', this.parentData);
    },
    receiveData(data) {
      this.parentData = data;
    }
  },
  components: {
    ChildComponent
  }
}
</script>
