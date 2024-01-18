<template>
  <div class="flowchart">
    <div class="flowchart-container">
      <div class="process">
        <div class="step" v-if="inputNumber !== null && inputNumber !== undefined">
          <p>Input Number: {{ inputNumber }}</p>
        </div>
        <div class="step" v-if="inputNumber !== null && inputNumber !== undefined">
          <p class="even" v-if="isEven(inputNumber)">The number is even.</p>
          <p class="odd" v-else>The number is odd.</p>
        </div>
        <div class="step" v-else>
          <p>Add number</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    inputNumber: Number,
  },
  methods: {
    isEven(number) {
      return number % 2 === 0;
    },
  },
};
</script>

<style scoped>
.flowchart {
  margin-top: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.flowchart-container {
  display: flex;
  flex-direction: column;
}

.process {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.step {
  background-color: #f0f8ff; /* AliceBlue */
  border: 2px solid #4682b4; /* SteelBlue */
  border-radius: 8px;
  padding: 10px;
  margin: 10px 0;
}

.even {
  color: #008000; /* Green */
}

.odd {
  color: #ff0000; /* Red */
}
</style>
