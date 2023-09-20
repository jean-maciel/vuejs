<script lang="ts">
import { defineComponent } from "vue";
import timerComponent from "./Timer.vue";

export default defineComponent({
  name: "newForm",
  components: {
    timerComponent,
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
        <timer-component></timer-component>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
