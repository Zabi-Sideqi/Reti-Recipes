# Reti Recipes

Reti Recipes is a modern recipe application built with **Vue.js** and **TypeScript**.  
The project aims to fetch recipes from an API, display them on a web page, and allow users to save their favorite recipes.

---

## Features

- **Fetch Recipes from API**: Uses [TheMealDB API](https://www.themealdb.com/) to search and display recipes.  
- **Favorites Management**: Users can add or remove recipes from their favorites. Favorites are stored locally in the browser's Local Storage.  
- **Responsive Design**: Optimized for both mobile devices and desktop.  
- **Search Functionality**: Ability to search for recipes by keyword.  
- **Navigation**: Includes multiple pages, "Home", "Favorites", "Login", and "Sign Up", handled via Vue Router.  
- **Recipe Details**: Dynamic routes to show details for specific recipes.  
- **404 Page**: Custom page for invalid URLs.  
- **Router Guards**: Protects certain pages from unauthorized access, such as "Favorites".

---

## Requirements Fulfillment

### **Pass**
The project meets all requirements for passing:

1. **Vue Application**:  
   The project is built using Vue.js.

2. **TypeScript**:  
   TypeScript is used throughout the project for typing.

3. **Text Interpolation**:  
   Used to display data, e.g., `{{ recipe.title }}` in `RecipeList.vue`.

4. **Conditional Rendering**:  
   Implemented with `v-if` to show or hide recipe information.

5. **List Rendering**:  
   `v-for` is used to render lists of recipes.

6. **Events (v-on or shorthand)**:  
   `@click` is used to handle user interactions, e.g., adding recipes to favorites.

7. **Computed Properties**:  
   Used to calculate data dynamically, e.g., filtering recipe lists.

8. **v-model**:  
   Two-way binding is used in `SearchForm.vue` to handle search input.

9. **Two Pages with Vue Router**:  
   The application has at least two pages: "Home" and "Favorites", among others.

10. **Props (Type-Safe)**:  
    Props are used in components and properly typed with TypeScript, e.g., in `RecipeList.vue`.

11. **Reactive State (ref())**:  
    Reactive state is managed with `ref()` in various parts of the application, e.g., login status.

12. **Lifecycle Hooks (mounted)**:  
    `onMounted()` is used to fetch data from the API when the page loads.

13. **Web Requests (fetch/axios)**:  
    Axios is used to fetch recipe data from TheMealDB.

14. **AI Usage**:  
    AI has been used to generate, structure, and optimize parts of the code and documentation.

### **Distinction**
The project meets the following requirements for distinction:

1. **Error Handling and Validation**:  
   Basic error handling is implemented for API calls (e.g., failed fetch responses), and search input is validated in `SearchForm.vue`.

2. **Dynamic Route Matching**:  
   The `/recipe/:id` route displays details for specific recipes.

3. **Router Guards**:  
   Favorites page is protected via a `beforeEach` guard.

4. **404 Page**:  
   Custom page displayed when visiting invalid URLs.

---

## Technologies and Libraries

- **Vue.js**: Frontend framework  
- **TypeScript**: For improved type safety and code quality  
- **Vue Router**: Handles navigation and dynamic routes  
- **Axios**: For API requests  
- **Express**: Backend server  
- **Concurrently**: Runs server and client simultaneously  
- **Local Storage**: Stores user favorites

---

## Installation

1. Clone the project:
   ```bash
   git clone <repository-url>

   ```

2. Navigate to the project folder::
   ```bash
   cd <project-folder>
   ```

3. Install dependencies::
   ```bash
   npm install
   ```

4. Start the application::
   ```bash
   npm run dev
   ```

5. Open the application in your browser at `http://localhost:3000`.

---

## Project Structure

```
|-- server              # Backend-server
├── src
│   ├── assets          # Bilder och globala resurser
│   ├── components      # Vue-komponenter
│   ├── composables     # Återanvändbara logiska funktioner
│   ├── router          # Vue Router-konfiguration
│   ├── types           # TypeScript-typer
│   ├── views           # Sidkomponenter
│   └── App.vue         # Huvudkomponent
├── public              # Statiska filer
└── README.md           # Projektbeskrivning
```

---

## Backend-server

The backend is built with Express and provides::

- **Recipe Fetching**: Fetches recipes from TheMealDB API.
- **Favorites Management**: Allows users to add, fetch, and remove favorite recipes. favoritrecept.
- **Port Handling**: Checks if a port is occupied and switches to another if needed.

The server starts automatically when running `npm run dev`.

---

## Possible Improvements

- Implement better error handling for API calls.
- Implement global state management if Pinia is allowed in the future.
- Add more tests to ensure code robustness.
- Expand the design for an even better user experience.

---

## Author (Zabi)

The project was developed as part of a course to improve understanding of Vue.js and TypeScript.

