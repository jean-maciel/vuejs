<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "stopwatchComponent",
  props: {
    time: { type: Number, default: 0 },
  },
  computed: {
    passedTime(): string {
      return new Date(this.time * 1000).toISOString().substring(11, 19);
    },
  },
});
</script>

<template>
  <section>
    <strong> {{ passedTime }}</strong>
  </section>
</template>

<style scoped></style>
