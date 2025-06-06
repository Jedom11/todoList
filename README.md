# 📝 ToDo List App

A productivity and gamified task management application combining Pomodoro technique, project organization, and interactive virtual pets. This app is designed to make your daily tasks more engaging through themes, behaviors, and animated feedback.

---

## 📦 Core Entities

### 1. **User**
Represents an individual using the application.
- `username`: string
- `email`: string
- `password`: string
- Functions: `login()`, `logout()`

### 2. **Project**
A user's workspace for organizing related tasklists and activities.
- `projectName`: string
- `createdAt`: timestamp
- Each user can have multiple projects.

### 3. **Tasklist**
A logical container within a project to group related tasks.
- `title`: string
- `description`: string
- Each project can have multiple tasklists.

### 4. **Task**
A specific action to be completed, optionally with subtasks.
- `description`: string
- `finished`: boolean
- Tasks can contain multiple `subtasks`.
- Each task belongs to a tasklist.

### 5. **Pomodoro Session**
Used to track focused work periods per project.
- `durationFocus`: int
- `durationRest`: int
- Sessions are linked to a specific project.
- Tracks: `totalNumPomodoros`, `actualNumPomodoros`

### 6. **Theme**
Defines the visual and interactive context of a project.
- `title`: string
- `description`: string
- Each project has one theme.

### 7. **Pet**
A motivational companion tied to a project, influenced by user productivity.
- `name`: string
- `getMood()`: determines mood based on performance.
- Moods include: `FRUSTRATED`, `SAD`, `SLEEPY`, `NEUTRAL`, `HAPPY`, `EXCITED`, `INSPIRED`

---

## 🔁 Relationships

- **User** 1 ⟶ * **Projects**
- **Project** 1 ⟶ * **Tasklists**
- **Tasklist** 1 ⟶ * **Tasks**
- **Task** 1 ⟶ * **Subtasks**
- **Project** 1 ⟶ * **Pomodoro Sessions**
- **Project** 1 ⟶ 1 **Theme**
- **Project** 1 ⟶ 1 **Pet**

---

## 🎭 Pet Behavior & Mood System

Each pet reacts to the user's productivity with a `Mood` that drives its `Behavior`, which includes animations and feedback phrases.

### `Mood` Enum
- `FRUSTRATED`, `SAD`, `SLEEPY`, `NEUTRAL`, `HAPPY`, `EXCITED`, `INSPIRED`

### `Behavior`
- `phrasesList`: array of motivational or emotional phrases
- `animations`: list of visual feedback (linked by mood)

### `Animation`
- `animationID`: UUID
- `name`: string
- `type`: enum `TypeAnimation` → `IDLE`, `ACTION`, `TRANSITION`
- `filePath`: animation asset path

---

## Features

### User
1. Sign up and login a User

### Projects Managment
1. CRUD of a project
2. Select a theme and a pet (associated to the theme selected)
3. Dashboard visualization in the project's home view

### Tasklists Managment
1. CRUD of a tasklist
2. Task can be add to a tasklist in the tasklist view
3. Task can be remove to a tasklist in the tasklist view
4. Session can be edited (number of pomodoros required, minutes of focus and rest)
5. Session can be started or cancelled.

### Task
1. CRUD of task
2. Task can be add at the home page view; selecting the project and the tasklist.


## 🎨 Available Themes

Each theme includes its own pets, scenarios, and Pomodoro clock designs:

### 1. **Pokémon**
- **Pets**: Pikachu, Piplup, Lucario
- **Scenario**: Professor's Lab
- **Pomodoro Clock**: Pokéball that fills up

### 2. **Hello Kitty**
- **Pets**: Hello Kitty, My Melody, Kuromi
- **Scenario**: Cute Coffee Restaurant
- **Pomodoro Clock**: Pastel board game

### 3. **Kirby**
- **Pets**: Kirby, King Dedede, Elfilin
- **Scenario**: Kirby’s Star World
- **Pomodoro Clock**: Kirby's hammer 
