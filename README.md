Filamzfik 🎞️
A Cinematic Photography Social Platform
Filamzfik is a full-stack web application that gives photographers a structured, intentional alternative to conventional social media. Instead of infinite scrolling feeds and engagement metrics, Filamzfik presents images in cinematic triptych layouts (1×3 or 3×1) — inspired by film strips and editorial spreads — putting the focus on visual storytelling over popularity.

🔗 Links

Live Demo: coming soon
Final Paper: see repository root
Video Presentation: https://www.youtube.com/watch?v=[YOUR_VIDEO_ID]


✨ Features

User Authentication — Secure registration and login with JWT + bcrypt
Triptych Layout Engine — Publish photos in structured 1×3 or 3×1 cinematic sequences
Cloud Image Storage — Fast, direct-to-S3 uploads via pre-signed URLs
Portfolio Profiles — Public-facing profile pages with curated triptych grids
Content Discovery — Browse and filter posts by aesthetic category tags
Minimal Engagement — Save posts and comment; no public like counts or follower metrics


🛠️ Tech Stack
LayerTechnologyFrontendReact 18, CSS Modules, Framer MotionBackendNode.js 20, Express.jsDatabasePostgreSQL 15, Sequelize ORMStorageAWS S3 (pre-signed URL pattern)AuthJWT, bcryptVersion ControlGit, GitHub

🚀 Getting Started
Prerequisites

Node.js v18+
PostgreSQL 15+
AWS account with an S3 bucket configured
Git

1. Clone the Repository
bashgit clone https://github.com/firdouspopal/filamzfik.git
cd filamzfik
2. Install Dependencies
bash# Backend
cd server
npm install

# Frontend
cd ../client
npm install
3. Configure Environment Variables
Create a .env file in the /server directory:
envPORT=5000
DATABASE_URL=postgresql://your_user:your_password@localhost:5432/filamzfik
JWT_SECRET=your_jwt_secret_here
AWS_ACCESS_KEY_ID=your_aws_key
AWS_SECRET_ACCESS_KEY=your_aws_secret
AWS_REGION=us-east-1
S3_BUCKET_NAME=your_bucket_name
Create a .env file in the /client directory:
envREACT_APP_API_URL=http://localhost:5000
4. Set Up the Database
bashcd server
npx sequelize-cli db:create
npx sequelize-cli db:migrate
5. Run the Application
bash# Start the backend (from /server)
npm run dev

# Start the frontend (from /client)
npm start
The app will be available at http://localhost:3000.

📁 Project Structure
filamzfik/
├── client/                  # React frontend
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── pages/           # Route-level page components
│   │   ├── hooks/           # Custom React hooks
│   │   └── utils/           # Helper functions
│   └── public/
├── server/                  # Express backend
│   ├── routes/              # API route handlers
│   ├── middleware/          # Auth and validation middleware
│   ├── models/              # Sequelize database models
│   ├── controllers/         # Business logic
│   └── config/              # Database and AWS config
└── README.md

🗄️ Database Schema
users — id, username, email, password_hash, bio, avatar_url, created_at
posts — id, user_id, title, caption, layout_type (1x3 | 3x1), created_at
post_images — id, post_id, s3_key, position, width, height
tags — id, post_id, label

🧪 Running Tests
bash# Backend API tests
cd server
npm test

# Frontend component tests
cd client
npm test

📄 License
This project was created as a capstone project for academic purposes.

👤 Author
Firdous Popal — Capstone Project, April 2026
