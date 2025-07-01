# Taskmate - React To-Do App 📝

<img width="1275" alt="Screenshot 2024-08-25 at 07 01 05" src="https://github.com/user-attachments/assets/37019d27-7829-45d6-8e41-7b4253bbb8c9">

---

## Project Summary

Taskmate is a modern, feature-rich To-Do list application built using React. It empowers users to add, edit, delete, and manage their daily tasks, with the added ability to toggle between light and dark themes. Built for both learning and productivity, Taskmate leverages local storage for persistence and is styled using TailwindCSS and Flowbite for a beautiful, responsive interface.

Whether you are new to React or looking for a practical project example, Taskmate offers a hands-on experience with core React concepts, component-based architecture, state management, routing, and more.

- **Live-Demo:** [https://taskmate-arnob.netlify.app/](https://taskmate-arnob.netlify.app/)

---

## Table of Contents

- [Project Summary](#project-summary)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Setup & Installation](#setup--installation)
- [Available Scripts](#available-scripts)
- [Functionality & Workflow](#functionality--workflow)
- [Components Overview](#components-overview)
- [API & Routing](#api--routing)
- [Learning and Teaching Guide](#learning-and-teaching-guide)
- [Example Usage & Scripts](#example-usage--scripts)
- [Keywords](#keywords)
- [Conclusion](#conclusion)

---

## Features

- Add, edit, delete tasks (To-Dos)
- Toggle between light and dark themes
- Data persistence using local storage
- Responsive UI with TailwindCSS and Flowbite
- React Router for navigation
- Clean, modular codebase ideal for learning

---

## Technology Stack

- **React** (via Create React App)
- **TailwindCSS** (utility-first CSS framework)
- **Flowbite** (UI component library for Tailwind)
- **React Router DOM** (routing)
- **LocalStorage API** (for task persistence)
- **Node.js & npm** (environment & package management)

---

## Project Structure

Typical structure (assuming default Create React App plus custom components):

```
Taskmate-To-Do--React/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── components/
│   │   ├── TodoList.js
│   │   ├── TodoItem.js
│   │   ├── ThemeToggle.js
│   │   └── ...
│   ├── App.js
│   ├── index.js
│   ├── App.css
│   └── ...
├── package.json
├── tailwind.config.js
├── README.md
└── ...
```

> **Note:** The exact file/folder names may differ; check your `src` directory for details.

---

## Setup & Installation

### Prerequisites

- **Node.js**: Install from [nodejs.org](https://nodejs.org/en/)
- **npm**: Comes bundled with Node.js

### 1. Clone the repository

```sh
git clone https://github.com/arnobt78/Taskmate-To-Do--React.git
cd Taskmate-To-Do--React
```

### 2. Install project dependencies

```sh
npm install
```

### 3. Install React Router

```sh
npm install react-router-dom
```
> [React Router Documentation](https://reactrouter.com/en/main)

### 4. Install TailwindCSS

Follow the official instructions:  
[https://tailwindcss.com/docs/installation](https://tailwindcss.com/docs/installation)

### 5. Install Flowbite (TailwindCSS Framework)

Follow the official instructions:  
[https://flowbite.com/docs/getting-started/quickstart/](https://flowbite.com/docs/getting-started/quickstart/)

---

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in development mode.  
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.  
The page will reload with changes, and lint errors will appear in the console.

---

### `npm test`

Launches the test runner in interactive watch mode.  
See [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more info.

---

### `npm run build`

Builds the app for production to the `build` folder.  
Optimizes React for best performance and minifies the output.

---

### `npm run eject`

**Note:** This is a one-way operation. Once you eject, you can't go back!  
Copies all configuration files and dependencies into your project, giving you full control.

---

## Functionality & Workflow

### How It Works

1. **Add Task**:  
   Enter a task in the input field and submit. The task appears in the list below.

2. **Edit Task**:  
   Click the edit icon/button next to a task to modify its text and save changes.

3. **Delete Task**:  
   Click the delete icon/button to remove a task from the list.

4. **Theme Toggle**:  
   Use the theme toggle button to switch between light and dark modes. The preference is saved locally.

5. **Persistence**:  
   All tasks and theme preferences are saved in your browser's local storage, so they persist after reloading or closing the browser.

---

## Components Overview

- **App.js**: Root component. Handles layout, routing, and global state.
- **TodoList.js**: Displays the list of tasks. Manages adding, editing, and deleting.
- **TodoItem.js**: Renders each individual task with edit/delete controls.
- **ThemeToggle.js**: Switches between light and dark themes.
- **Other Components**: You may have modals, notification components, or others for enhanced UX.

---

## API & Routing

- **API**: No external API—data is managed locally via localStorage.
- **Routing**:  
  Implemented with `react-router-dom` for multi-page navigation (e.g., About, Home, etc.).

**Example:**
```jsx
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

<Router>
  <Switch>
    <Route path="/" exact component={Home} />
    <Route path="/about" component={About} />
    {/* Add more routes as needed */}
  </Switch>
</Router>
```

---

## Learning and Teaching Guide

This project demonstrates:

- **React fundamentals**: components, props, state, hooks
- **Component-based architecture**: each logical unit in its own file
- **Persistent state with LocalStorage**
- **Styling with TailwindCSS**: utility-first, responsive design
- **Reusable UI components with Flowbite**
- **Routing with React Router**
- **Best practices**: folder structure, code organization, and more

**Perfect for:**
- Beginners learning React
- Demonstrating CRUD operations
- Showcasing modern frontend workflow

---

## Example Usage & Scripts

### Add a Task (Example Code)
```jsx
const [tasks, setTasks] = useState([]);

function addTask(taskText) {
  const newTask = { id: Date.now(), text: taskText, completed: false };
  setTasks([...tasks, newTask]);
  localStorage.setItem('tasks', JSON.stringify([...tasks, newTask]));
}
```
---

### Edit a Task (Example Code)
```jsx
function editTask(id, newText) {
  const updatedTasks = tasks.map(task =>
    task.id === id ? { ...task, text: newText } : task
  );
  setTasks(updatedTasks);
  localStorage.setItem('tasks', JSON.stringify(updatedTasks));
}
```
---

### Delete a Task (Example Code)
```jsx
function deleteTask(id) {
  const updatedTasks = tasks.filter(task => task.id !== id);
  setTasks(updatedTasks);
  localStorage.setItem('tasks', JSON.stringify(updatedTasks));
}
```
---

### Theme Toggle (Example Code)
```jsx
const [darkMode, setDarkMode] = useState(false);

function toggleTheme() {
  setDarkMode(!darkMode);
  localStorage.setItem('theme', !darkMode ? 'dark' : 'light');
}
```
---

## Keywords

- React
- To-Do App
- CRUD
- LocalStorage
- TailwindCSS
- Flowbite
- React Router
- Theme Toggle
- Component-based Architecture
- Web Development

---

## Conclusion

Taskmate is a practical, easy-to-understand project for learning and sharing core React concepts, modern CSS, and essential web development patterns. Explore, modify, and expand it as you wish!

---

## Additional Resources

- [Create React App Documentation](https://facebook.github.io/create-react-app/docs/getting-started)
- [React Documentation](https://reactjs.org/)
- [TailwindCSS Docs](https://tailwindcss.com/docs/installation)
- [Flowbite Docs](https://flowbite.com/docs/)
- [React Router Docs](https://reactrouter.com/en/main)

---

## Happy Coding! 🎉

Thank you for using and sharing Taskmate.  
Feel free to contribute or provide feedback!

---
