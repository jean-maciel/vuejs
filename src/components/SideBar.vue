<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SideBar",
});
</script>

<template>
  <header>
    <h1>
      <img alt="" src="../assets/logo.png" />
    </h1>
  </header>
</template>

<style scoped>
header {
  padding: 1rem;
  background: aquamarine;
  width: 100%;
  height: 100vh;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
