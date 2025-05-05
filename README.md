
# Kanban Style Task Board

A simple Kanban Style board built using Next js , `@dnd-kit` for drag-and-drop functionality, and a backend server for managing tasks. This project provides a drag-and-drop interface for managing tasks across three columns: "To Do", "In Progress", and "Done".

## Features

- **Drag and Drop**: Use `@dnd-kit` to drag and drop tasks between columns.
- **Task Management**: Add, update, and organize tasks easily.
- **CRUD Operations**: Interact with a backend API for fetching, updating, and storing tasks.
- **Responsive Design**: Optimized for mobile and desktop views.

## Architecture

This application consists of the following parts:

1. **Frontend (React)**: The user interface is built with React, utilizing hooks like `useState` and `useEffect` to manage state and lifecycle events. The Kanban board uses drag-and-drop functionality provided by `@dnd-kit/core`.

2. **Backend (JSON Server)**: A simple backend is used to store tasks. The backend serves tasks from a JSON file and allows CRUD operations. It runs on `localhost:4000`.

3. **Styling**: The app uses Tailwind CSS for styling the user interface and ensuring a responsive layout.

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
cd kanban-board
```

### 2. Install Dependencies

Install the necessary dependencies for the frontend and backend:

```bash
npm install
```

### 3. Set Up the Backend

You need to run a simple backend server to manage tasks. You can use **JSON Server** for this purpose.

- Install **JSON Server** globally if you haven't already:

```bash
npm install -g json-server
```

- Inside the project folder, create a `db.json` file for the backend:

```json
{
  "todos": [
    {
      "id": "1",
      "title": "Buy groceries",
      "description": "Milk, eggs, bread, and vegetables",
      "status": "todo"
    },
    {
      "id": "2",
      "title": "Clean the house",
      "description": "Vacuum, dust, and organize shelves",
      "status": "inprogress"
    },
    {
      "id": "3",
      "title": "Finish reading book",
      "description": "Read the last two chapters of the novel",
      "status": "done"
    }
  ]
}
```

- Run the JSON server:

```bash
json-server --watch db.json --port 4000
```

This will start a local server that listens on `http://localhost:4000` and will serve your task data.

### 4. Run the Frontend

To run the frontend, in the project directory, run:

```bash
npm start
```

This will start the React app on `http://localhost:3000`.

### 5. Access the Application

- Open your browser and go to `http://localhost:3000` to access the Kanban board.
- You should see the drag-and-drop board with tasks fetched from the backend.

### 6. Interact with the App

- **Add Tasks**: You can add new tasks through the provided form.
- **Drag and Drop**: Tasks can be dragged between the "To Do", "In Progress", and "Done" columns.
- **Update Tasks**: The task's status will be updated both on the board and in the backend when dragged.

## Approach

The application is built with a **React-based front end** that uses **React Hooks** (`useState`, `useEffect`) to manage the state and interact with the backend.

### Frontend Components:

1. **`Home.js`**: The main Kanban board, which displays tasks categorized into three columns: "To Do", "In Progress", and "Done". Drag-and-drop functionality is implemented using `@dnd-kit/core`.
2. **`Task.js`**: Represents individual tasks that are draggable.
3. **`Draggable.js`**: A wrapper component to make tasks draggable.
4. **`AddTask.js`**: Form to add new tasks to the board, communicating with the backend.
5. **`Loading.js`**: A simple loading spinner shown while fetching tasks.

### Backend:

The backend is a **JSON Server** that serves task data stored in a `db.json` file. The server supports CRUD operations on tasks:

- **GET /todos**: Fetch all tasks.
- **POST /todos**: Add a new task.
- **PATCH /todos/:id**: Update a task (used for drag-and-drop operations).
- **DELETE /todos/:id**: Delete a task (this feature is not yet implemented in the frontend).

### Drag-and-Drop:

The drag-and-drop functionality is powered by **@dnd-kit/core**. We use `useDroppable` for defining the columns and `useDraggable` for each task. When a task is dropped in a new column, the task's status is updated on the backend via a `PATCH` request.

---

## Contributing

Feel free to fork the project, open an issue, or submit a pull request if you want to contribute to this project.

## License

This project is open-source and available under the [MIT License](LICENSE).
