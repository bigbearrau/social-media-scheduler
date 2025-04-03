# Social Media Scheduler

## 🚀 Overview
A web-based platform that connects to TikTok, YouTube, Twitter, Instagram, and Facebook APIs, allowing users to schedule posts across multiple platforms from one central dashboard.

## ✨ Features
- **OAuth Authentication**: Securely connect and manage social media accounts.
- **Post Scheduling**: Automate content posting for multiple platforms.
- **Content Management**: Upload, edit, and organize posts.
- **Queue System**: Uses Redis + BullMQ for handling scheduled posts.
- **Analytics Dashboard**: Track post performance (planned feature).

## 🛠️ Tech Stack
- **Frontend**: Next.js (React), Tailwind CSS
- **Backend**: Node.js (Express)
- **Database**: PostgreSQL / MongoDB
- **Queue System**: Redis + BullMQ
- **Authentication**: OAuth 2.0 (Google, TikTok, Facebook, Twitter, Instagram)
- **Storage**: AWS S3 / Firebase Storage

## 📦 Installation
### 1️⃣ Clone the repository:
```sh
git clone https://github.com/YOUR_USERNAME/social-media-scheduler.git
cd social-media-scheduler
```

### 2️⃣ Set up the backend:
```sh
cd backend
npm install
cp .env.example .env  # Add your API keys in the .env file
node server.js
```

### 3️⃣ Set up the frontend:
```sh
cd frontend
npm install
npm run dev
```

## 🔑 API Authentication Setup
### Get API Keys from:
- [TikTok Developer Portal](https://developers.tiktok.com/)
- [Google Cloud Console (YouTube)](https://console.cloud.google.com/)
- [Twitter Developer Portal](https://developer.twitter.com/)
- [Facebook/Instagram Developer Portal](https://developers.facebook.com/)

### Store keys in `.env`:
```
GOOGLE_CLIENT_ID=your-client-id
GOOGLE_CLIENT_SECRET=your-client-secret
TIKTOK_CLIENT_ID=your-tiktok-id
TIKTOK_CLIENT_SECRET=your-tiktok-secret
...
```

## ⏳ Scheduling Posts
The app uses **BullMQ (Redis)** to queue and process scheduled posts.
Example job queue setup:
```javascript
const { Queue } = require("bullmq");
const postQueue = new Queue("postQueue", { connection: { host: "localhost", port: 6379 } });

postQueue.add("newPost", { content: "Hello, world!", platform: "Twitter" }, { delay: 60000 });
```

## 🚀 Deployment
- **Frontend**: Deploy on Vercel or Netlify
- **Backend**: Deploy on AWS EC2, DigitalOcean, or Railway.app
- **Database**: Use Supabase, AWS RDS, or MongoDB Atlas

## 🏗️ Future Features
- **AI-generated captions**
- **Cross-platform content repurposing**
- **Advanced analytics & reporting**

## 📄 License
[MIT License](LICENSE)

## 🤝 Contributing
Pull requests are welcome! Please open an issue for discussions before submitting major changes.

---
Made with ❤️ by Robert Austin
