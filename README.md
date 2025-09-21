Lost and Found Application – Frontend

This is the frontend of the Lost and Found Application, built using React + TypeScript and integrated with a Spring Boot + JWT backend.
The application allows users to report, search, and manage lost/found items, with authentication, role-based navigation, and CRUD operations.
Features

JWT Authentication & Authorization

Protected Routing with role-based access

CRUD operations for lost and found items

Responsive UI with TailwindCSS

API integration with Spring Boot backend

Project Setup
1️⃣ Create React + TypeScript Project
npx create-react-app lost-and-found-frontend --template typescript
cd lost-and-found-frontend

2️⃣ Install Dependencies
npm install react-router-dom axios jwt-decode
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

3️⃣ Configure Tailwind (tailwind.config.js)
content: ["./src/*/.{js,ts,jsx,tsx}"],
theme: { extend: {} },
plugins: [],


Update index.css:

@tailwind base;
@tailwind components;
@tailwind utilities;

📁 Folder Structure
src/
├── api/          # API configuration (axios instance)
├── components/   # Reusable UI components
├── pages/        # Login, Signup, Dashboard, etc.
├── routes/       # Routing and ProtectedRoute
├── types/        # TypeScript types/interfaces
├── utils/        # Helper functions
├── App.tsx
└── main.tsx

Authentication

Axios instance with JWT support (api/axios.ts)

Login & Signup pages with token storage

ProtectedRoute for private routes

Token is stored in localStorage and automatically attached to API requests.

Routing

All routes are defined in routes/AppRoutes.tsx.

/login → Login page

/signup → User registration

/dashboard → Protected dashboard (requires login)

📝 CRUD Operations

Example: List reported items in Dashboard

useEffect(() => {
  API.get("/items").then((res) => setItems(res.data));
}, []);


Users can:

Report items (POST)

Update item status (PUT/PATCH)

Delete items (DELETE)

UI/UX Best Practices

Consistent TailwindCSS components (bg-blue-500, rounded-xl, shadow-md)

Responsive design with sm:, md:, lg: breakpoints

Clean layout with reusable components

🔃 GitHub Setup
git init
git add .
git commit -m "Initial front-end commit"
git remote add origin https://github.com/your-username/lost-and-found-frontend.git
git push -u origin master

Contribution

Fork the repo

Create a feature branch (git checkout -b feature-name)

Commit changes (git commit -m "Added feature X")

Push to branch (git push origin feature-name)

Create a Pull Request

📌 Notes

Ensure backend is running at http://localhost:8080

JWT tokens are expected in Authorization: Bearer <token> format

Update .env for custom API base URL if needed
