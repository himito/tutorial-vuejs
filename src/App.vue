<script setup lang="ts">
import { ref } from 'vue';

const isEmpty = ref(false);

function addTask(){
  alert('Add task');
}
</script>

<template>
   <div class="page">
    <div class="task-card">

      <h1 class="task-title">My Task Manager</h1>

      <!-- Add task -->
      <div class="add-row">
        <input type="text" class="task-input" placeholder="Enter a new task..." />
        <button class="btn-add" :disabled="isEmpty" @click="addTask"">Add</button>
      </div>

      <!-- Status + filters -->
      <div class="status-bar">
        <p class="status-text">3 of 4 tasks completed</p>
        <div class="filters">
          <button class="filter-pill filter-pill--active">All</button>
          <button class="filter-pill filter-pill--inactive">Todo</button>
          <button class="filter-pill filter-pill--inactive">Done</button>
        </div>
      </div>

      <!-- Task list -->
      <ul class="task-list">

        <li class="task-item task-item--done">
          <input type="checkbox" class="task-checkbox" checked />
          <span class="task-label task-label--done">Write the slides</span>
          <button class="btn-delete" aria-label="Delete task">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
              stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <polyline points="3 6 5 6 21 6" />
              <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2" />
              <line x1="10" y1="11" x2="10" y2="17" />
              <line x1="14" y1="11" x2="14" y2="17" />
            </svg>
          </button>
        </li>

        <li class="task-item task-item--done">
          <input type="checkbox" class="task-checkbox" checked />
          <span class="task-label task-label--done">Buy the train tickets</span>
          <button class="btn-delete" aria-label="Delete task">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
              stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <polyline points="3 6 5 6 21 6" />
              <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2" />
              <line x1="10" y1="11" x2="10" y2="17" />
              <line x1="14" y1="11" x2="14" y2="17" />
            </svg>
          </button>
        </li>

        <li class="task-item task-item--done">
          <input type="checkbox" class="task-checkbox" checked />
          <span class="task-label task-label--done">Configure the laptop</span>
          <button class="btn-delete" aria-label="Delete task">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
              stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <polyline points="3 6 5 6 21 6" />
              <path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2" />
              <line x1="10" y1="11" x2="10" y2="17" />
              <line x1="14" y1="11" x2="14" y2="17" />
            </svg>
          </button>
        </li>

        <li class="task-item task-item--pending">
          <input type="checkbox" class="task-checkbox" />
          <span class="task-label">Ask for some feedback</span>
          <button class="btn-delete" aria-label="Delete task">
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
