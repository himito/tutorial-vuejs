<script setup lang="ts">
import { computed, ref } from 'vue';
import TaskItem from './TaskItem.vue';

interface Task {
  id: number;
  title: string;
  done: boolean;
}

const props = defineProps<{
  tasks: Task[];
}>();
</script>

<template>
  <!-- Task list -->
  <div v-if="tasks.length === 0" class="empty-state">
    <p class="empty-state-text">No tasks yet. Add a task to get started!</p>
  </div>
  <ul class="task-list" v-else>
    <li v-for="task in tasks" class="task-item" :class="{ 'task-item--done': task.done }" :key="task.id">
      <TaskItem :task="task" />
    </li>
  </ul>
</template>