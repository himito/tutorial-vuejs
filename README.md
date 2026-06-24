# Todo App

A small task manager built with Vue 3, TypeScript, Vite, and Tailwind CSS.

The app lets you add tasks, mark them as complete, delete them, and filter the list by all, todo, or done tasks.

## Features

- Add a new task with the form or the Enter key
- Clear the input with Escape
- Mark tasks as done with a checkbox
- Delete tasks from the list
- Filter tasks by `All`, `Todo`, or `Done`
- Show a completion counter
- Shared TypeScript types for tasks and filters

## Tech Stack

- Vue 3
- TypeScript
- Vite
- Tailwind CSS
- ESLint and Oxlint
- Prettier

## Project Setup

Install dependencies:

```sh
npm install
```

Start the development server:

```sh
npm run dev
```

Build for production:

```sh
npm run build
```

Preview the production build:

```sh
npm run preview
```

Run linting:

```sh
npm run lint
```

Format source files:

```sh
npm run format
```

## Project Structure

```text
src/
  App.vue                    Main app state and task filtering
  main.ts                    Vue app entry point
  types.ts                   Shared TypeScript types
  assets/
    style.css                Tailwind and component styles
  components/
    AddTaskForm.vue          Task creation form
    FilterButtons.vue        Filter selector buttons
    TaskItem.vue             Single task row controls
    TaskList.vue             Empty state and task list rendering
```

## Notes

Tasks are currently stored in component state, so they reset when the page reloads. A future improvement would be saving tasks to `localStorage` or a backend API.

This project requires Node.js `^22.18.0` or `>=24.12.0`, as defined in `package.json`.
