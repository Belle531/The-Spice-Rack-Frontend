# Project Name and Short Description

The Spice Rack Frontend is the mobile-first user interface for the ultimate recipe community. Search, save, and share high-quality recipes using a clean, interactive design built with React and Tailwind CSS. Your kitchen companion.

Your Name

Cassandra A. Moore

Link to Capstone Plan

The full project plan is hosted in the backend repository: [link-to-cassandra-repo]

Technology Stack

React

Tailwind CSS

React Router

Axios / SWR


Capstone Project Plan: The Spice Rack (Recipe Sharing App)

1. Project Description and Purpose

Project Title: The Spice Rack
Purpose: The Spice Rack is a full-stack web application designed to be a modern, community-driven platform where users can discover, share, and save their favorite recipes. Its primary goal is to provide robust search and filtering capabilities (by ingredients, cuisine, and user ratings) and a clean, responsive interface to encourage user engagement and content contribution. This project will demonstrate proficiency in relational data modeling, API design, and modern front-end development with secure user authentication.

2. Planned Technology Stack

This project will utilize a full-stack JavaScript environment with a focus on relational data and server-side performance.

Frontend: React (functional components and hooks)

Styling: Tailwind CSS (for rapid, responsive UI development)

Backend Framework: Node.js with Express

Database: PostgreSQL (simulating an RDS environment)

ORM: Prisma (for type-safe and efficient database queries)

Authentication: JWT (JSON Web Tokens)

3. Core API Routes

The backend will focus on five main entities: Users, Recipes, Ingredients, Favorites, and Reviews.

Entity

HTTP Method

Route Path

Description

Protected?

Auth

POST

/api/auth/register

Creates a new user account.

No

Auth

POST

/api/auth/login

Authenticates user and returns a JWT.

No

Recipes

POST

/api/recipes

Creates a new recipe (requires auth).

Yes

Recipes

GET

/api/recipes

Retrieves all recipes with filtering/search query parameters.

No

Recipes

GET

/api/recipes/:id

Retrieves a single recipe by its ID, including ingredients and reviews.

No

Recipes

PUT

/api/recipes/:id

Updates an existing recipe (User must be the recipe owner).

Yes

Recipes

DELETE

/api/recipes/:id

Deletes a recipe (User must be the recipe owner).

Yes

Favorites

POST

/api/recipes/:id/favorite

Toggles the recipe as a favorite for the current user.

Yes

Reviews

POST

/api/recipes/:id/reviews

Submits a new rating and review for a recipe.

Yes

Users

GET

/api/users/profile

Retrieves the profile, user's recipes, and favorites of the authenticated user.

Yes

Users

GET

/api/users/:id

Retrieves the profile of any user.

No

4. Frontend Features and Pages

The frontend will be built using React and Tailwind CSS.

Page/Component

Key Features and Functionality

Home/Feed

Displays a feed of recent and highly-rated recipes. Includes a primary search bar and quick filters (e.g., "Dinner," "Dessert").

Recipe Detail Page

Shows full recipe details, allowing users to view ingredients, instructions, and community reviews. Features the Favorite button and the Review/Rating submission form.

Create Recipe Page

A protected route with a dynamic form for submitting a new recipe, including fields for adding multiple ingredients and steps.

User Profile Page (Protected)

Displays the user's uploaded recipes and their list of favorited recipes.

Login/Register

Pages for handling user authentication.

Search Results

Dedicated page to display results from comprehensive search queries (ingredient filtering, cuisine, etc.).

5. Authentication Flow

Method: Email/Password authentication using JWT (JSON Web Tokens).

Registration/Login: User submits credentials. Server validates, hashes passwords (bcrypt), and generates a JWT.

Token Management: The JWT is securely sent back and stored on the client (preferably in HTTP-only cookies for production, or localStorage for development).

Protected Routes: When accessing protected API routes (e.g., creating a recipe), the client attaches the JWT in the Authorization: Bearer <token> header. The Express middleware verifies the token and sets the user context for the request.

Protected Routes/Pages:
The routes marked Yes in Section 3 are protected. The corresponding frontend pages are Create Recipe Page and User Profile Page.

6. Deployment Plan

Component

Service

Notes

Frontend (Client)

Vercel

Deployment of the static React build.

Backend (API)

Render

Simple container deployment for the Node.js/Express application.

Database

Render PostgreSQL

Managed relational database service.

Setup Steps / Environment Variables:

Backend Secrets: The API server requires environment variables for the database connection string (DATABASE_URL), the JWT secret key (JWT_SECRET), and the port (PORT). These will be configured as secrets on Render.

Frontend Config: The client requires the base URL of the deployed backend API (VITE_API_BASE_URL).

7. Key NPM Libraries / Tools

Backend (Node/Express)

express: Core web application framework.

prisma: ORM for PostgreSQL, handling database migrations and queries.

bcrypt: Secure password hashing and verification.

jsonwebtoken: JWT token creation and verification.

dotenv: Loading environment variables for local development.

Frontend (React)

react-router-dom: Client-side routing.

axios: Promise-based HTTP client for API calls.

tailwindcss: Utility-first CSS framework for styling.

lucide-react: Modern icon library.

swr or react-query: For efficient data fetching and caching.
