<script lang="ts">
import { defineComponent } from "vue";
import stopwatchComponent from "@/components/Stopwatch.vue";

export default defineComponent({
  name: "timerComponent",
  components: { stopwatchComponent },
  data() {
    return { time: 0, stopwatch: 0, isRunning: false };
  },
  methods: {
    start() {
      this.isRunning = true;
      this.stopwatch = setInterval(() => this.time++, 1000);
    },
    stop() {
      this.isRunning = false;
      clearInterval(this.stopwatch);
    },
  },
});
</script>

<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <stopwatch-component :time="time"></stopwatch-component>
    <button :disabled="isRunning" class="button" @click="start">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button :disabled="!isRunning" class="button" @click="stop">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<style scoped></style>
