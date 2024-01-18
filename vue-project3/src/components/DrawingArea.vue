<template>
  <div>
    <div id="drawing-area" @click="adjustCircleSize">
      <div v-if="showCircle" :style="{ width: circleDiameter + 'px', height: circleDiameter + 'px' }" class="circle"></div>
    </div>

    <div>
      <label for="radiusInput">Circle Radius:</label>
      <input type="number" id="radiusInput" v-model="circleRadius" @input="updateCircleSize">
      <button @click="eraseCircle">Erase</button>
    </div>

    
  </div>
</template>

<script>
export default {
  data() {
    return {
      showCircle: true,
      circleRadius: 50,
    };
  },
  computed: {
    circleDiameter() {
      return this.circleRadius * 2;
    },
  },
  methods: {
    adjustCircleSize(event) {
      const { offsetX, offsetY } = event;
      const centerX = event.currentTarget.offsetWidth / 2;
      const centerY = event.currentTarget.offsetHeight / 2;

      this.circleRadius = Math.min(Math.abs(centerX - offsetX), Math.abs(centerY - offsetY));
    },
    eraseCircle() {
      this.circleRadius = 0
    },
    updateCircleSize() {
      // Ensure the radius is a positive value
      this.circleRadius = Math.abs(this.circleRadius);
    },
  },
};
</script>

<style scoped>
#drawing-area {
  position: relative;
  width: 300px;
  height: 300px;
  border: 1px solid #ccc;
  margin-bottom: 1rem;
}

.circle {
  position: absolute;
  border-radius: 50%;
  background-color: lightblue;
}
</style>
