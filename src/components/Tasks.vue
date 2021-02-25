<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
      <Task
        :task="task"
        @delete="onDeleteTask"
        @toggle-reminder="toggleReminer"
      ></Task>
    </div>
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  methods: {
    onDeleteTask(id) {
      this.$emit("delete-task", id);
    },
    toggleReminer(id) {
      this.$emit("toggle-reminder", id);
    },
  },
};
</script>

<style scoped>
</style>