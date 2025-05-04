# Kanban Task Board

A simple Kanban board built using React (with JSX), `@dnd-kit` for drag-and-drop functionality, and a backend server for managing tasks. This project provides a drag-and-drop interface for managing tasks across three columns: "To Do", "In Progress", and "Done".

## Features

- **Drag and Drop**: Use `@dnd-kit` to drag and drop tasks between columns.
- **Task Management**: Add, update, and organize tasks easily.
- **Responsive Design**: Optimized for mobile and desktop views.
- **CRUD Operations**: Interact with a backend API for fetching, updating, and storing tasks.

## Architecture

This application consists of the following parts:

1. **Frontend (React)**: The user interface is built with React, utilizing hooks like `useState` and `useEffect` to manage state and lifecycle events. The Kanban board uses drag-and-drop functionality provided by `@dnd-kit/core`.

2. ** Backend (JSON Server) **: A simple backend stores tasks. It serves tasks from a JSON file and allows CRUD operations. It runs on `localhost:4000`.

3. **Styling**: The app uses Tailwind CSS to style the user interface and ensure a responsive layout.

4. **Drag-and-Drop**: The drag-and-drop functionality is powered by `@dnd-kit`. Tasks can be dragged between three columns: "To Do", "In Progress", and "Done".

## Prerequisites

Before running the project, ensure you have the following installed:

- Node.js (v14 or higher)
- npm or yarn
- JSON Server (for the backend)

## Instructions to Run the Project Locally

### 1. Clone the Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/swapneshp18/DropoTask.git
cd DropoTask
