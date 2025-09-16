# Reti Recipes

Reti Recipes is a modern recipe application built with **Vue.js** and **TypeScript**.  
It fetches recipes from an API, displays them in a clean interface, and allows users to save their favorite recipes locally.  

---

##  Features

- **Fetch Recipes from API**: Uses [TheMealDB API](https://www.themealdb.com/) to search and display recipes.  
- **Favorites Management**: Add or remove recipes from favorites, stored locally in the browser.  
- **Responsive Design**: Works seamlessly on mobile, tablet, and desktop.  
- **Search Functionality**: Search for recipes by keyword.  
- **Navigation**: Includes multiple pages (`Home`, `Favorites`, `Login`, `Sign Up`) using Vue Router.  
- **Recipe Details**: View recipe details on dynamic routes (`/recipe/:id`).  
- **Protected Routes**: Favorites page is only accessible when logged in.  
- **Custom 404 Page**: Handles invalid routes gracefully.  

---

##  Screenshots

> Place your screenshots in `/src/assets/screenshots/` and update the filenames.

### Home Page  
![Home Page](src/assets/screenshots/home.png)


### Favorites Page  
![Favorites Page](src/assets/screenshots/favorites.png)

### Mobile View  
![Mobile View](src/assets/screenshots/mobile.png)

---

## Getting Started

### Prerequisites

Make sure you have installed:  
- [Node.js](https://nodejs.org/) (>=16)  
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)  

### Installation


# Clone the repository
git clone <repository-url>

# Navigate to project folder
cd <project-folder>

# Install dependencies
npm install

# Start the application
npm run dev

##  Project Structure

```text
|-- server              # Backend server
├── src
│   ├── assets          # Images and global resources
│   │   └── screenshots # Screenshots for README
│   ├── components      # Vue components
│   ├── composables     # Reusable logic (custom hooks)
│   ├── router          # Vue Router configuration
│   ├── types           # TypeScript type definitions
│   ├── views           # Page components
│   └── App.vue         # Root component
├── public              # Static files
└── README.md           # Project documentation





