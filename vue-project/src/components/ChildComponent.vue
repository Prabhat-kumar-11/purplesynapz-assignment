<!-- ChildComponent.vue -->
<template>
  <div>
    <button @click="sendData">Send Data to Parent</button>
    <p>Child Data: {{ childData }}</p>
  </div>
</template>

<script>
export default {
  props: ['childData'],
  methods: {
    sendData() {
      this.$emit('childEvent', { name: 'Alice', age: 30 });
    }
  }
}
</script>
