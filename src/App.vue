<script setup lang="ts">
import { computed, ref } from 'vue';

import TaskList from './components/TaskList.vue';
import FilterButtons from './components/FilterButtons.vue';
import AddTaskForm from './components/AddTaskForm.vue';

// function addTask() {
//   if (!newTaskTitle.value.trim()) return;

//   // Add a new task to the list
//   tasks.value.push({
//     id: tasks.value.length + 1,
//     title: newTaskTitle.value,
//     done: false
//   });

//   // reset the input field
//   newTaskTitle.value = '';
// }

interface Task {
  id: number;
  title: string;
  done: boolean;
}

const tasks = ref<Task[]>([]);

const doneCount = computed(
  () => tasks.value.filter(t => t.done).length
)


</script>

<template>
  <div class="page">
    <div class="task-card">

      <h1 class="task-title">My Task Manager</h1>

      <!-- Add Task Form -->
      <AddTaskForm />

      <!-- Status + filters -->
      <div class="status-bar">
        <p class="status-text">{{ doneCount }} of {{ tasks.length }} tasks completed</p>
        <FilterButtons />
      </div>

      <!-- Task List -->
      <TaskList />

    </div>
  </div>
</template>

<style scoped></style>