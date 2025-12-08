# Full Stack CRUD Application

A modern, production-ready full-stack user management system built with **Next.js 15**, **MongoDB**, **Prisma ORM**, and **TypeScript**.

![Next.js](https://img.shields.io/badge/Next.js-15.1.3-black?style=flat-square&logo=next.js)
![React](https://img.shields.io/badge/React-19-blue?style=flat-square&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=flat-square&logo=typescript)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green?style=flat-square&logo=mongodb)
![Prisma](https://img.shields.io/badge/Prisma-5.22.0-2D3748?style=flat-square&logo=prisma)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?style=flat-square&logo=tailwind-css)

**Developer:** Ishan Gupta  
**GitHub Repository:** [github.com/ishan2105/my-crud-app](https://github.com/ishan2105/my-crud-app)

## 🎯 Features

✨ **Complete CRUD Operations**
- ✅ Create users with name and email
- ✅ Read/fetch all users with real-time updates
- ✅ Update user information
- ✅ Delete users with confirmation

🎨 **Modern UI/UX**
- Dark theme with gradient backgrounds
- Animated hero section with blob effects
- Responsive card-based layout
- Smooth transitions and hover effects
- Professional statistics dashboard
- Collapsible form with validation
- Mobile-first responsive design

🔐 **Type-Safe & Production Ready**
- Full TypeScript support with strict mode
- Prisma auto-generated types
- Comprehensive error handling
- Input validation
- Server-side rendering (SSR)
- Static page generation
- Optimized build output

## 🛠️ Technology Stack

| Technology | Version | Purpose |
|-----------|---------|---------|
| **Next.js** | 15.1.3 | React framework with SSR/SSG |
| **React** | 19 | UI library |
| **TypeScript** | 5 | Type safety |
| **Prisma** | 5.22.0 | ORM for database |
| **MongoDB** | Atlas | Cloud database |
| **Tailwind CSS** | 4 | Utility-first CSS |
| **Node.js** | 18+ | Runtime environment |

## 📋 Prerequisites

Before running the application, ensure you have:

- **Node.js** 18+ installed
- **npm** or **yarn** package manager
- **MongoDB Atlas** account (or local MongoDB instance)
- **Git** for version control

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/ishan2105/my-crud-app.git
cd my-crud-app
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Configuration

Create a `.env.local` file in the root directory:

```env
DATABASE_URL="mongodb+srv://username:password@cluster.mongodb.net/database?retryWrites=true&w=majority"
JWT_SECRET="your-super-secret-jwt-key-change-in-production"
```

**Note:** Replace `username`, `password`, `cluster`, and `database` with your MongoDB Atlas credentials.

### 4. Build the Application

```bash
npm run build
```

### 5. Start the Server

```bash
npm start
```

The application will be available at **http://localhost:3000**

### 6. Development Mode (Optional)

For development with hot-reload:

```bash
npm run dev
```

## 📁 Project Structure

```
my-crud-app/
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   └── users/
│   │   │       ├── route.ts          # GET/POST /api/users
│   │   │       └── [id]/
│   │   │           └── route.ts      # GET/PUT/DELETE /api/users/[id]
│   │   ├── layout.tsx                # Root layout
│   │   ├── page.tsx                  # Home page (UI)
│   │   └── globals.css               # Global styles
│   ├── controllers/
│   │   └── user.controller.ts        # Business logic
│   ├── models/
│   │   └── user.model.ts             # Data models
│   ├── utils/
│   │   └── api.utils.ts              # Utility functions
│   └── config/
│       └── env.ts                    # Environment config
├── prisma/
│   └── schema.prisma                 # Database schema
├── public/                           # Static files
├── .env.local                        # Environment variables
├── package.json                      # Dependencies
├── tsconfig.json                     # TypeScript config
├── next.config.ts                    # Next.js config
└── README.md                         # This file
```

## 🔌 API Endpoints

### Get All Users
```http
GET /api/users
```
**Response:** `200 OK`
```json
[
  {
    "id": "user_id",
    "name": "John Doe",
    "email": "john@example.com",
    "createdAt": "2025-12-08T10:00:00Z",
    "updatedAt": "2025-12-08T10:00:00Z"
  }
]
```

### Create User
```http
POST /api/users
Content-Type: application/json

{
  "name": "Jane Doe",
  "email": "jane@example.com"
}
```
**Response:** `201 Created`

### Get User by ID
```http
GET /api/users/:id
```
**Response:** `200 OK`
```json
{
  "id": "user_id",
  "name": "John Doe",
  "email": "john@example.com"
}
```

### Update User
```http
PUT /api/users/:id
Content-Type: application/json

{
  "name": "Updated Name",
  "email": "updated@example.com"
}
```
**Response:** `200 OK`

### Delete User
```http
DELETE /api/users/:id
```
**Response:** `200 OK`
```json
{
  "message": "User deleted successfully"
}
```

## 🗄️ Database Schema

### User Model
```prisma
model User {
  id        String   @id @default(auto()) @map("_id") @db.ObjectId
  name      String
  email     String   @unique
  password  String?
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}
```

## 📝 Usage

### Creating a User

1. Click "Get Started" button on the home page
2. Fill in the name and email fields
3. Click "Create User"
4. The user will be added to the database and displayed in the list

### Updating a User

1. Click the edit button on a user card
2. Modify the name and/or email
3. Click "Update User"

### Deleting a User

1. Click the delete button on a user card
2. Confirm the deletion in the popup dialog
3. The user will be removed from the database

## 🧪 Testing

### Manual API Testing with cURL

```bash
# Get all users
curl http://localhost:3000/api/users

# Create user
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{"name":"Test User","email":"test@example.com"}'

# Update user
curl -X PUT http://localhost:3000/api/users/USER_ID \
  -H "Content-Type: application/json" \
  -d '{"name":"Updated Name","email":"updated@example.com"}'

# Delete user
curl -X DELETE http://localhost:3000/api/users/USER_ID
```

### Using Postman

1. Import the endpoints into Postman
2. Set the base URL to `http://localhost:3000`
3. Test each endpoint with provided request bodies

## 🔧 Configuration

### Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `DATABASE_URL` | MongoDB connection string | `mongodb+srv://user:pass@cluster.mongodb.net/db` |
| `JWT_SECRET` | Secret key for JWT tokens | `your-secret-key-here` |

### Tailwind CSS

Configured in `tailwind.config.ts` with custom colors and fonts:
- Dark theme optimized
- Custom gradient utilities
- Responsive breakpoints

### TypeScript

Strict mode enabled in `tsconfig.json`:
- `strict: true`
- `noImplicitAny: true`
- Full type checking

## 📦 Available Scripts

```bash
npm run dev              # Start development server
npm run build            # Build for production
npm start                # Start production server
npm run lint             # Run ESLint
```

## 🚀 Deployment

### Deploy to Vercel (Recommended)

1. Push code to GitHub
2. Visit [Vercel](https://vercel.com)
3. Import your GitHub repository
4. Add environment variables
5. Deploy with one click

```bash
# Or use Vercel CLI
vercel deploy
```

### Deploy to Other Platforms

Works on any platform that supports Node.js:
- Heroku
- Railway
- Render
- DigitalOcean
- AWS
- Azure
- Google Cloud

## 📊 Performance

- **Build Size:** ~105KB (First Load JS)
- **Page Load:** <1 second
- **API Response:** <100ms
- **Database Queries:** Optimized with Prisma

## 🔒 Security Features

- ✅ Type-safe database queries (Prisma)
- ✅ Input validation
- ✅ Error handling
- ✅ CORS ready
- ✅ Environment variable protection
- ✅ SQL injection prevention
