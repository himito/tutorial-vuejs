<script setup lang="ts">
import { computed, ref } from 'vue';
import TaskItem from './TaskItem.vue';

interface Task {
  id: number;
  title: string;
  done: boolean;
}

const model = defineModel<Task[]>({ default: () => [] });

function deleteTask(id: number) {
  model.value = model.value.filter(task => task.id !== id);
}

</script>

<template>
  <!-- Task list -->
  <div v-if="model.length === 0" class="empty-state">
    <p class="empty-state-text">No tasks yet. Add a task to get started!</p>
  </div>
  <ul class="task-list" v-else>
    <li v-for="task in model" class="task-item" :class="{ 'task-item--done': task.done }" :key="task.id">
      <TaskItem :task="task" @delete-task="deleteTask" />
    </li>
  </ul>
</template>