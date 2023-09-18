<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar></SideBar>
    </div>
    <div class="column is-three-quarter">
      <newForm></newForm>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "@/components/SideBar.vue";
import newForm from "@/components/Form.vue";

export default defineComponent({
  name: "App",
  components: { SideBar, newForm },
});
</script>

<style></style>
