# SkillSwap - Complete Learning Ecosystem

**SkillSwap** is a community-driven skill exchange platform where users can teach, learn, exchange skills, buy courses, book professional teachers, and build a skill-based network — all through a clean, modern, and user-friendly interface.

## 🌟 Features

### Core Features
- **User Profiles** - Complete profile management with skills, bio, and achievements
- **Skill Management** - Add skills you can teach and skills you want to learn
- **Intelligent Matching** - AI-powered algorithm to match users based on skill compatibility
- **Peer-to-Peer Skill Swap** - Exchange skills with matching partners for free
- **Video Courses Marketplace** - Browse and purchase structured video courses
- **Premium Teachers** - Book one-on-one sessions with professional instructors
- **Real-time Messaging** - In-app chat system with Socket.io
- **Connections Network** - Build your professional learning network
- **Progress Tracking** - Track your learning journey with stats and achievements
- **Dashboard** - Personalized dashboard with recommendations

## 🚀 Technology Stack

### Frontend
- **React.js** - UI framework
- **React Router** - Navigation
- **Axios** - HTTP client
- **Socket.io Client** - Real-time communication
- **React Icons** - Icon library
- **React Toastify** - Notifications

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **JWT** - Authentication
- **Socket.io** - Real-time messaging
- **Bcrypt** - Password hashing

## 📦 Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd "Skill Swap"
   ```

2. **Install dependencies**
   ```bash
   npm run install-all
   ```
   Or install separately:
   ```bash
   npm install
   cd server && npm install
   cd ../client && npm install
   ```

3. **Configure environment variables**
   
   Create a `.env` file in the `server` directory:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/skillswap
   JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
   ```

4. **Start MongoDB**
   ```bash
   # If using local MongoDB
   mongod
   ```

5. **Run the application**
   
   Development mode (runs both server and client):
   ```bash
   npm run dev
   ```
   
   Or run separately:
   ```bash
   # Terminal 1 - Backend
   cd server
   npm run dev
   
   # Terminal 2 - Frontend
   cd client
   npm start
   ```

6. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

## 📁 Project Structure

```
Skill Swap/
├── client/                 # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── context/        # React context (Auth)
│   │   ├── pages/          # Page components
│   │   ├── App.js          # Main app component
│   │   └── index.js        # Entry point
│   └── package.json
├── server/                 # Node.js backend
│   ├── models/             # MongoDB models
│   ├── routes/             # API routes
│   ├── middleware/         # Auth middleware
│   ├── index.js            # Server entry point
│   └── package.json
└── package.json            # Root package.json
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user

### Users
- `GET /api/users/me` - Get current user
- `GET /api/users/:id` - Get user by ID
- `PUT /api/users/me` - Update user profile

### Skills
- `POST /api/skills/teach` - Add skill to teach
- `POST /api/skills/learn` - Add skill to learn
- `DELETE /api/skills/teach/:id` - Remove skill to teach
- `DELETE /api/skills/learn/:id` - Remove skill to learn
- `GET /api/skills/me` - Get user's skills

### Matches
- `GET /api/matches` - Get skill matches
- `GET /api/matches/courses` - Get recommended courses
- `GET /api/matches/teachers` - Get recommended teachers

### Courses
- `GET /api/courses` - Get all courses
- `GET /api/courses/:id` - Get course by ID
- `POST /api/courses` - Create course (instructor)
- `POST /api/courses/:id/reviews` - Add review

### Teachers
- `GET /api/teachers` - Get all teachers
- `GET /api/teachers/:id` - Get teacher by ID
- `POST /api/teachers/register` - Register as teacher

### Messages
- `GET /api/messages/conversations` - Get all conversations
- `GET /api/messages/conversation/:userId` - Get conversation
- `POST /api/messages` - Send message
- `PUT /api/messages/read/:userId` - Mark as read

### Connections
- `GET /api/connections` - Get connections
- `POST /api/connections/:userId` - Add connection
- `DELETE /api/connections/:userId` - Remove connection

## 🎨 Features in Detail

### 1. Skill Matching Algorithm
The platform uses an intelligent algorithm that:
- Matches users who want to learn what others teach
- Identifies perfect skill swaps (mutual exchange)
- Calculates match scores based on skill compatibility
- Recommends courses and teachers based on learning goals

### 2. Real-time Messaging
- Socket.io integration for instant messaging
- Read receipts
- Conversation management
- Message history

### 3. User Dashboard
- Quick stats overview
- Recommended matches
- Suggested courses
- Recent activity

### 4. Profile Management
- Edit profile information
- Manage skills (teach/learn)
- View achievements and ratings
- Track progress

## 🔒 Authentication

The application uses JWT (JSON Web Tokens) for authentication. Tokens are stored in localStorage and sent with each API request via the Authorization header.

## 🗄️ Database Models

- **User** - User profiles, skills, connections
- **Course** - Video courses with lessons
- **Teacher** - Premium teacher profiles
- **Message** - Chat messages
- **Session** - Learning sessions (swap/premium)

## 🎯 Use Cases

1. **Skill Exchange** - Find someone who wants to learn your skill while you learn theirs
2. **Structured Learning** - Purchase video courses for comprehensive learning
3. **Professional Training** - Book sessions with verified expert teachers
4. **Networking** - Connect with like-minded learners and teachers
5. **Progress Tracking** - Monitor your learning journey

## 🚧 Future Enhancements

- Video/audio call integration
- Payment gateway integration
- Advanced search and filters
- Skill verification badges
- Group learning sessions
- Mobile app (React Native)
- Email notifications
- File sharing in messages

## 📝 License

MIT License

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Contact

For questions or support, please open an issue in the repository.

---

**Built with ❤️ for the learning community**


