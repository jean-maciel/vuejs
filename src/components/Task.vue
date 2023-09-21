<script lang="ts">
import { defineComponent, PropType } from "vue";
import StopwatchComponent from "@/components/Stopwatch.vue";
import ITask from "@/interfaces/ITask";
import BoxComponent from "@/components/Box.vue";

export default defineComponent({
  name: "taskComponent",
  components: { BoxComponent, StopwatchComponent },
  props: {
    task: {
      type: Object as PropType<ITask>,
      required: true,
    },
  },
});
</script>

<template>
  <box-component>
    <div class="columns">
      <div class="column is-7">{{ task.description || "No description" }}</div>
      <div class="column">
        <StopwatchComponent :time="task.duration"></StopwatchComponent>
      </div>
    </div>
  </box-component>
</template>

<style scoped></style>
