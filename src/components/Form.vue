<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "newForm",
  data() {
    return { time: 0, stopwatch: 0 };
  },
  computed: {
    passedTime(): string {
      return new Date(this.time * 1000).toISOString().substring(11, 19);
    },
  },
  methods: {
    start() {
      this.stopwatch = setInterval(() => this.time++, 1000);
    },
    stop() {
      clearInterval(this.stopwatch);
    },
  },
});
</script>

<template>
  <div class="box">
    <div class="columns">
      <div aria-label="New task form" class="column is-8" role="form">
        <input class="input" placeholder="Task" type="text" />
      </div>
      <div class="column">
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <section>
            <strong> {{ passedTime }}</strong>
          </section>
          <button class="button" @click="start">
            <span class="icon">
              <i class="fas fa-play"></i>
            </span>
            <span>play</span>
          </button>
          <button class="button" @click="stop">
            <span class="icon">
              <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
