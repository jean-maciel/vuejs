<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SideBar",
  emits: ["onThemeChange"],
  data() {
    return {
      darkModeOn: false,
    };
  },
  computed: {
    buttonText() {
      if (this.darkModeOn) {
        return "Deactivate dark mode";
      }
      return "Activate dark mode";
    },
  },
  methods: {
    changeTheme() {
      this.darkModeOn = !this.darkModeOn;
      this.$emit("onThemeChange", this.darkModeOn);
    },
  },
});
</script>

<template>
  <header>
    <h1>
      <img alt="" src="../assets/logo.png" />
    </h1>
    <button class="button" @click="changeTheme">{{ buttonText }}</button>
  </header>
</template>

<style scoped>
header {
  padding: 1rem;
  background: aquamarine;
  width: 100%;
  height: 100vh;
  text-align: center;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
