<script setup lang="ts">
import { computed, ref } from 'vue';

const newTaskTitle = ref('');

interface Task {
  id: number;
  title: string;
  done: boolean;
}

const tasks = ref<Task[]>([
  { id: 1, title: 'Configure the laptop', done: true },
  { id: 2, title: 'Ask for some feedback', done: false },
]);

function addTask(){
}

function deleteTask(id: number){
  alert(`Delete task: ${id}`);
}

function filterTasks(filter: string){
  alert(`Filter tasks: ${filter}`);
}

const doneCount = computed(
  () => tasks.value.filter(t => t.done).length
)
</script>

<template>
   <div class="page">
    <div class="task-card">

      <h1 class="task-title">My Task Manager</h1>

      <!-- Add task -->
      <div class="add-row">
        <input type="text" class="task-input" placeholder="Enter a new task..." v-model="newTaskTitle" />
        <button class="btn-add" :disabled="!newTaskTitle.trim()" @click="addTask"">Add</button>
      </div>

      <!-- Status + filters -->
      <div class="status-bar">
        <p class="status-text">{{ doneCount }} of {{ tasks.length }} tasks completed</p>
        <div class="filters">
          <button class="filter-pill filter-pill--active" @click="filterTasks('all')">All</button>
          <button class="filter-pill filter-pill--inactive" @click="filterTasks('todo')">Todo</button>
          <button class="filter-pill filter-pill--inactive" @click="filterTasks('done')">Done</button>
        </div>
      </div>

      <!-- Task list -->
      <div v-if="tasks.length === 0" class="empty-state">
        <p class="empty-state-text">No tasks yet. Add a task to get started!</p>
      </div>
      <ul class="task-list" v-else>
        <li v-for="task in tasks" class="task-item" :class="{ 'task-item--done': task.done }" :key="task.id">
          <input type="checkbox" class="task-checkbox" :checked="task.done" />
          <span class="task-label" :class="{ 'task-label--done': task.done }">{{ task.title }}</span>
          <button class="btn-delete" aria-label="Delete task" @click="deleteTask(task.id)">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
              stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <polyline points="3 6 5 6 21 6" />
              <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2" />
              <line x1="10" y1="11" x2="10" y2="17" />
              <line x1="14" y1="11" x2="14" y2="17" />
            </svg>
          </button>
        </li>
      </ul>
    </div>
  </div>
 </template>

<style scoped></style>
