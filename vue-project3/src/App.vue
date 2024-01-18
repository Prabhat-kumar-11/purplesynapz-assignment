<template>
  <div id="app">
    <DrawingArea />
  </div>
</template>

<script>
import DrawingArea from "@/components/DrawingArea.vue";

export default {
  components: {
    DrawingArea,
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 2rem;
}

</style>
