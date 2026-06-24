<script setup lang="ts">
import type { Task } from '@/types';

import TaskItem from './TaskItem.vue';

defineProps<{
  tasks: Task[]
}>()

defineEmits<{
  (e: 'delete-task', id: number): void
}>()

</script>

<template>
  <!-- Task list -->
  <div v-if="tasks.length === 0" class="empty-state">
    <p class="empty-state-text">No tasks yet. Add a task to get started!</p>
  </div>
  <ul class="task-list" v-else>
    <li v-for="task in tasks" class="task-item" :class="{ 'task-item--done': task.done }" :key="task.id">
      <TaskItem :task="task" @delete-task="$emit('delete-task', task.id)" />
    </li>
  </ul>
</template>
