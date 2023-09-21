<script lang="ts">
import { defineComponent } from "vue";
import timerComponent from "./Timer.vue";

export default defineComponent({
  name: "newForm",
  emits: ["saveTask"],
  components: {
    timerComponent,
  },
  data() {
    return { description: "" };
  },
  methods: {
    finishTask(time: number): void {
      this.$emit("saveTask", { duration: time, description: this.description });
      this.description = "";
    },
  },
});
</script>

<template>
  <div class="box form">
    <div class="columns">
      <div aria-label="New task form" class="column is-8" role="form">
        <input
          v-model="description"
          class="input"
          placeholder="Task"
          type="text"
        />
      </div>
      <div class="column">
        <timer-component @when-finished="finishTask"></timer-component>
      </div>
    </div>
  </div>
</template>

<style>
.form {
  color: var(--primary-text);
  background-color: var(--primary-bg);
}
</style>
