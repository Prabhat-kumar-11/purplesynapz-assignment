<template>
  <div>
    <InputField @update-flowchart="updateFlowchart" />
    <Flowchart :inputNumber="inputNumber" />
    <button @click="resetFlowchart">Reset</button>
  </div>
</template>

<script>
import InputField from "@/components/InputField.vue";
import Flowchart from "@/components/flowchart.vue";

export default {
  components: {
    InputField,
    Flowchart,
  },
  data() {
    return {
      inputNumber: null,
    };
  },
  methods: {
    updateFlowchart(number) {
      this.inputNumber = number;
    },
    resetFlowchart() {
      this.inputNumber = null;
    },
  },
};
</script>
