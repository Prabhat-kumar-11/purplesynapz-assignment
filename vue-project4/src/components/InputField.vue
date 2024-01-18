<template>
  <div class="input-field">
    <label for="numberInput">Enter Number:</label>
    <input
      id="numberInput"
      type="number"
      v-model="inputNumber"
      @input="updateFlowchart"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputNumber: null,
    };
  },
  methods: {
    updateFlowchart() {
      this.$emit("update-flowchart", this.inputNumber);
    },
  },
};
</script>

<style scoped>
.input-field {
  margin-bottom: 20px;
  background-color: #f0f0f0; /* Light grey background color */
  padding: 10px;
  border-radius: 8px;
}

label {
  font-weight: bold;
  margin-right: 10px;
}

input {
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
  width: 200px; /* Adjust as needed */
}
</style>
