<script setup lang="ts">
import { ref } from 'vue';

type Filter = 'all' | 'todo' | 'done';

const model = defineModel<Filter>({ default: () => 'all' });

const filterOptions: { label: string; value: Filter }[] = [
  { label: 'All', value: 'all' },
  { label: 'Todo', value: 'todo' },
  { label: 'Done', value: 'done' },
];


function filterPillClass(value: Filter) {
  return model.value === value ? 'filter-pill--active' : 'filter-pill--inactive';
}
</script>

<template>
  <div class="filters">
    <button v-for="option in filterOptions" :key="option.value" class="filter-pill"
      :class="filterPillClass(option.value)" @click="model = option.value">
      {{ option.label }}
    </button>
  </div>
</template>