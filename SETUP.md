# Quick Setup Guide

## Step-by-Step Setup

### 1. Install Dependencies
```bash
npm run install-all
```

### 2. Setup MongoDB

**Option A: Local MongoDB**
- Install MongoDB on your system
- Start MongoDB service: `mongod`
- Default connection: `mongodb://localhost:27017/skillswap`

**Option B: MongoDB Atlas (Cloud)**
- Create account at https://www.mongodb.com/cloud/atlas
- Create a cluster and get connection string
- Use connection string in `.env` file

### 3. Configure Environment

Create `server/.env` file:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/skillswap
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
```

### 4. Run the Application

**Development Mode (Both Server & Client):**
```bash
npm run dev
```

**Or Run Separately:**

Terminal 1 (Backend):
```bash
cd server
npm run dev
```

Terminal 2 (Frontend):
```bash
cd client
npm start
```

### 5. Access the Application

- **Frontend:** http://localhost:3000
- **Backend API:** http://localhost:5000

### 6. First Steps

1. Register a new account
2. Add skills you can teach
3. Add skills you want to learn
4. Explore matches in the Matches section
5. Connect with other users
6. Start messaging!

## Troubleshooting

### Port Already in Use
- Change PORT in `server/.env`
- Or kill process using port 5000/3000

### MongoDB Connection Error
- Ensure MongoDB is running
- Check connection string in `.env`
- Verify MongoDB service is active

### Module Not Found
- Delete `node_modules` folders
- Run `npm run install-all` again

### Socket.io Connection Issues
- Ensure backend is running on port 5000
- Check CORS settings in `server/index.js`

## Testing the Application

1. **Create Test Users:**
   - Register multiple accounts
   - Add different skills to each
   - Test matching algorithm

2. **Test Features:**
   - Skill matching
   - Messaging
   - Connections
   - Profile updates

## Production Deployment

1. Build frontend:
   ```bash
   cd client
   npm run build
   ```

2. Set production environment variables
3. Use process manager (PM2) for Node.js
4. Configure reverse proxy (Nginx)
5. Enable HTTPS

