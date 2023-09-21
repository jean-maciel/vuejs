<template>
  <main
    :class="{ 'dark-mode': darkModeOn }"
    class="columns is-gapless is-multiline"
  >
    <div class="column is-one-quarter">
      <SideBar @on-theme-change="changeTheme"></SideBar>
    </div>
    <div class="column is-three-quarter content">
      <newForm @saveTask="saveTask"></newForm>
      <div class="list">
        <TaskComponent
          v-for="(task, index) in tasks"
          :key="index"
          :task="task"
        ></TaskComponent>
        <box-component v-if="isListEmpty">No tasks yet.</box-component>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SideBar from "@/components/SideBar.vue";
import newForm from "@/components/Form.vue";
import TaskComponent from "@/components/Task.vue";
import ITask from "@/interfaces/ITask";
import BoxComponent from "@/components/Box.vue";

export default defineComponent({
  name: "App",
  components: { BoxComponent, TaskComponent, SideBar, newForm },
  data() {
    return { tasks: [] as ITask[], darkModeOn: false };
  },
  computed: {
    isListEmpty(): boolean {
      return this.tasks.length === 0;
    },
  },
  methods: {
    saveTask(task: ITask) {
      this.tasks.push(task);
    },
    changeTheme(darkModeOn: boolean) {
      this.darkModeOn = darkModeOn;
    },
  },
});
</script>

<style>
.list {
  padding: 1.25rem;
}

main {
  --primary-bg: #fff;
  --primary-text: #000;
}

main.dark-mode {
  --primary-bg: #2b2d42;
  --primary-text: #ddd;
}

.content {
  background: var(--primary-bg);
}
</style>
