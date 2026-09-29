# 🎬 TMDB Movie Search App

A modern movie search web application built with **React** and **Vite**, using the **TMDB (The Movie Database) API** to search and display movie information.

The project focuses on learning and applying **React components, state management, API integration, asynchronous JavaScript, environment variables, and responsive UI development**.

---

## 🚀 Live Demo

🔗 **Live Demo:** [Add your deployed URL here]

---

## 📸 Preview

> Add screenshots or GIFs of your application here.

```text
┌─────────────────────────────────────────────────────┐
│                    🎬 Movie App                     │
│                                                     │
│       🔍 Search for movies...                       │
│                                                     │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐          │
│   │  Movie   │  │  Movie   │  │  Movie   │          │
│   │  Poster  │  │  Poster  │  │  Poster  │          │
│   │          │  │          │  │          │          │
│   └──────────┘  └──────────┘  └──────────┘          │
└─────────────────────────────────────────────────────┘
```

---

## ✨ Features

* 🔎 Search for movies using the TMDB API
* 🎬 Display movie search results dynamically
* 🖼️ Display movie posters
* ⭐ Display movie information such as title and rating
* ⚡ Fast development and production builds with Vite
* 🧩 Reusable React components
* 🔄 Fetch data from an external REST API
* 🌐 Responsive user interface
* 🔐 API key stored securely using environment variables
* ⏳ Loading and API request handling
* ❌ Error handling for failed API requests

---

## 🛠️ Technologies Used

| Technology             | Purpose                                |
| ---------------------- | -------------------------------------- |
| **React**              | Building the user interface            |
| **Vite**               | Development environment and build tool |
| **JavaScript (ES6+)**  | Application logic                      |
| **TMDB API**           | Movie data                             |
| **CSS / Tailwind CSS** | Styling and responsive design          |
| **Fetch API**          | Communicating with TMDB                |
| **Git & GitHub**       | Version control                        |

---

## 📂 Project Structure

```text
movie-search-app/
│
├── public/
│
├── src/
│   ├── assets/
│   │
│   ├── components/
│   │   ├── MovieCard.jsx
│   │   └── Search.jsx
│   │
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
│
├── .env
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
└── README.md
```

> Your exact folder structure may differ depending on how the project is organized.

---

## 🔑 TMDB API Setup

This project uses the **TMDB API** to retrieve movie information.

### 1. Create a TMDB Account

Visit:

**https://www.themoviedb.org/**

Create an account and generate an API key from your account settings.

### 2. Create the Environment File

Create a `.env` file in the root directory:

```env
VITE_TMDB_API_KEY=your_tmdb_api_key
```

### 3. Access the API Key

In Vite, environment variables prefixed with `VITE_` can be accessed through:

```javascript
const API_KEY = import.meta.env.VITE_TMDB_API_KEY;
```

⚠️ **Important:** Never commit your actual API key to GitHub.

Add the following to `.gitignore`:

```gitignore
.env
.env.local
.env.*.local
```

---

## 🔌 API Configuration

The application communicates with the TMDB API using HTTP requests.

Example API configuration:

```javascript
const API_BASE_URL = 'https://api.themoviedb.org/3';

const API_OPTIONS = {
  method: 'GET',
  headers: {
    accept: 'application/json',
    Authorization: `Bearer ${API_KEY}`
  }
};
```

The application can then request movie data from TMDB and use the returned JSON data to render movie cards.

---

## ⚛️ React Concepts Used

This project was created to practice several important React concepts.

### Components

The application is divided into reusable components.

For example:

```jsx
const MovieCard = ({ movie }) => {
  return (
    <div>
      <p>{movie.title}</p>
    </div>
  );
};
```

### Props

Movie information is passed from a parent component to `MovieCard` using props.

```jsx
<MovieCard movie={movie} />
```

Inside the component:

```jsx
const MovieCard = ({ movie }) => {
  console.log(movie.title);
};
```

### State

React state is used to store dynamic application data such as:

* Search query
* Movie results
* Loading state
* Error state

Example:

```jsx
const [searchTerm, setSearchTerm] = useState('');
```

### useEffect

`useEffect` can be used to execute code when certain state values change, such as fetching movie data.

```jsx
useEffect(() => {
  fetchMovies();
}, []);
```

### Async / Await

API requests are handled asynchronously:

```javascript
const response = await fetch(url, API_OPTIONS);
const data = await response.json();
```

---

## 🔄 How the Application Works

The basic application flow is:

```text
User
  │
  ▼
Search for a movie
  │
  ▼
React updates search state
  │
  ▼
Application sends request
  │
  ▼
TMDB API
  │
  ▼
JSON Movie Data
  │
  ▼
React processes the response
  │
  ▼
MovieCard Components
  │
  ▼
Movie Results displayed
```

---

## 🧩 Example Movie Data

TMDB returns movie information in JSON format.

A simplified movie object might look like:

```json
{
  "id": 123,
  "title": "Example Movie",
  "overview": "An example movie description.",
  "poster_path": "/example.jpg",
  "vote_average": 8.2,
  "release_date": "2026-01-01"
}
```

React can then access individual properties:

```jsx
movie.id
movie.title
movie.overview
movie.poster_path
movie.vote_average
movie.release_date
```

---

## 💻 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
```

### 2. Navigate to the Project

```bash
cd your-repository-name
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure Environment Variables

Create a `.env` file:

```env
VITE_TMDB_API_KEY=your_tmdb_api_key
```

### 5. Start the Development Server

```bash
npm run dev
```

The application will be available at the local development URL shown by Vite.

---

## 📜 Available Scripts

| Command           | Description                          |
| ----------------- | ------------------------------------ |
| `npm run dev`     | Start the development server         |
| `npm run build`   | Build the application for production |
| `npm run preview` | Preview the production build         |
| `npm run lint`    | Run ESLint                           |

---

## 🧠 What I Learned

Through this project, I practiced:

* React component architecture
* Passing data using props
* React state management
* `useState`
* `useEffect`
* API integration
* REST APIs
* Fetch requests
* Async/Await
* JSON data handling
* Environment variables with Vite
* Conditional rendering
* Loading states
* Error handling
* Dynamic rendering using `.map()`
* Working with external APIs
* Responsive UI development
* Git and GitHub workflow

---

## 🔮 Future Improvements

Possible improvements for future versions include:

* [ ] Movie details page
* [ ] Popular movies section
* [ ] Trending movies
* [ ] Genre filtering
* [ ] Movie sorting
* [ ] Pagination
* [ ] Infinite scrolling
* [ ] Favorites/watchlist
* [ ] User authentication
* [ ] Search history
* [ ] Debounced search
* [ ] Skeleton loading animations
* [ ] Better error messages
* [ ] Dark/light theme
* [ ] Improved accessibility
* [ ] Mobile-first UI improvements

---

## ⚠️ Disclaimer

This project uses the **TMDB API** to retrieve movie-related information.

This application is **not affiliated with or endorsed by TMDB**.

Movie data, images, ratings, and other information are provided by **The Movie Database (TMDB)**.

---

## 👨‍💻 Author

**Anupama Omiru Dasanayake**

Computer Science Undergraduate
University of Westminster

### 🌐 Connect With Me

* GitHub: [https://github.com/Anupama-Omiru-Dasanayake]
* LinkedIn: [https://linkedin.com/in/anupama-omiru-dasanayake]

---
