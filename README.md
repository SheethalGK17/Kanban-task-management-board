 Kanban Task Management Web App

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Screenshots and Demo](#screenshots-and-demo)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [State Management Notes](#state-management-notes)

## Overview

The app is designed to help users organize work visually by grouping tasks into boards and progress columns. It includes CRUD flows for boards and tasks, interactive subtasks, responsive navigation, and modal-driven editing experiences.

This repository focuses on the frontend experience only. The initial board data is loaded from a local JSON file and then managed in client-side Redux state.

## Features

Users can:

- View an optimized layout across mobile and desktop screen sizes
- Create, edit, and delete boards
- Add and remove columns when creating or editing a board
- Create, update, and delete tasks inside each board
- Move tasks by changing their status
- Drag tasks between columns
- Track progress through subtasks
- Toggle between light and dark themes
- Show or hide the sidebar on larger screens
- Use modal forms with validation for board and task updates

### Expected Behavior

#### Boards

- Selecting a board in the sidebar switches the active workspace
- Clicking `Create New Board` opens the board creation modal
- Editing a board updates its title and column list
- Deleting a board removes its columns and tasks after confirmation

#### Columns

- Tasks belong to board columns such as `Todo`, `Doing`, and `Done`
- Boards without columns cannot accept new tasks until at least one column is added
- Clicking `+ New Column` opens the board editor to extend the workflow

#### Tasks

- New tasks are appended to the selected column
- Editing a task can also move it into a different column
- Subtasks can be marked complete from the task details view
- Drag and drop allows tasks to be repositioned across columns

## Screenshots and Demo

### Screenshot

![Screenshot](https://user-images.githubusercontent.com/100496179/197352796-412b11a9-569c-49e9-95bd-a79776260cdd.png)

### Live Demo

- Live Site: (https://kanban-task-management-app.netlify.app/)

## Tech Stack

- React 18
- React Redux
- React Responsive
- CSS
- Semantic HTML
- Drag and Drop API
- Create React App

## Project Structure

```text
src/
  assets/         Static icons and logos
  components/     Core UI pieces such as Board, Column, Header, Sidebar, Task
  modals/         Modal flows for creating, editing, viewing, and deleting
  redux/          Global store plus board and theme slices
  styles/         App-wide and component-specific stylesheets
  data.json       Seed data used to initialize the board state
  App.js          Main application shell
  index.js        React entry point and Redux provider setup
```

## Getting Started

### Prerequisites

- Node.js 18 or newer recommended
- npm

### Installation

```bash
npm install
```

### Start the Development Server

```bash
npm start
```



### Create a Production Build

```bash
npm run build
```

## Available Scripts

### `npm start`

Runs the app in development mode with hot reload.

### `npm test`

Launches the test runner in interactive watch mode.

### `npm run build`

Builds the app for production into the `build` folder.

### `npm run eject`

Ejects the Create React App configuration. This action is permanent and usually unnecessary for small to medium projects.

## State Management Notes

The app uses Redux Toolkit slices to keep board and theme state centralized.

- `boardsSlice.js` handles board switching, board CRUD, task CRUD, subtask completion, drag-and-drop moves, and status-based task transfers
- `themeSlice.js` stores the active theme and toggles between `light` and `dark`
- `data.json` provides the initial board data loaded into the Redux store

At runtime, the UI reads the active board from global state and renders the header, sidebar, columns, tasks, and modal flows around it.

## Future Improvements

- Persist boards and tasks in local storage or a backend API
- Add user authentication and multi-user collaboration
- Improve accessibility for keyboard drag-and-drop interactions
- Add richer test coverage for reducers and modal workflows
- Introduce task due dates, labels, and filtering

