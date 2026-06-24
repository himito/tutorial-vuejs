<script setup lang="ts">
import { ref } from 'vue';

const newTaskTitle = ref('');

const emit = defineEmits<{
  (e: 'add-task', title: string): void
}>()

function addTask() {
  emit('add-task', newTaskTitle.value.trim());
  newTaskTitle.value = '';
}
</script>

<template>
  <!-- Add task -->
  <div class="add-row">
    <input type="text" class="task-input" placeholder="Enter a new task..." v-model="newTaskTitle"
      @keyup.enter="addTask" @keyup.esc="newTaskTitle = ''" />
    <button class="btn-add" :disabled="!newTaskTitle.trim()" @click="addTask">Add</button>
  </div>
</template>