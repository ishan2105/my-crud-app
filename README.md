📝 my-crud-app

A simple, clean and beginner-friendly CRUD (Create, Read, Update, Delete) project built using Next.js, TypeScript, Prisma, and MongoDB.
This project shows how a real-world full-stack app works — from UI to backend to database — in a way that's easy to understand and extend.

⭐ What this app can do

Add new users

Edit existing users

Delete users

View the complete user list

Fast UI updates and clean design

Uses modern full-stack tools used in real companies

🚀 Tech Stack

Next.js 15

React 19

TypeScript

Prisma ORM

MongoDB Atlas

Tailwind CSS

💻 How to run locally (PowerShell users)

Run these commands inside your project folder:

1️⃣ Install dependencies
npm install

2️⃣ Create .env.local
notepad .env.local


Add:

DATABASE_URL="your MongoDB connection string"
JWT_SECRET="any-secure-random-string"

3️⃣ Start the project
npm run dev


Now open:
👉 http://localhost:3000

📦 Build for production
npm run build
npm start

📁 Folder Structure
src/
 ├─ app/            # UI pages + API routes
 ├─ controllers/    # Logic for handling requests
 ├─ models/         # Types and interfaces
 ├─ utils/          # Helper functions
 └─ config/         # Environment + config files

prisma/
 └─ schema.prisma   # Database schema

🌐 Deployment (Vercel)

Just push changes to GitHub — Vercel auto-deploys the project.
If Vercel ever shows build errors, simply:

npm install
git add .
git commit -m "update deps"
git push


Then Redeploy without cache on Vercel.

🎯 Why this project exists

This project is made to practice and showcase:

full-stack development skills

clean code

database integration

API routes

modern React
Perfect for portfolio, interviews, and learning real production tools.

✨ Author

Ishan Gupta
Feel free to explore and modify the project.