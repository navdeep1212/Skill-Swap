# Quick Fix: Server Error - MongoDB Not Connected

## The Problem
Your server is showing "server error" because **MongoDB is not running**. The diagnostic shows:
```
❌ MongoDB connection failed!
Error: connect ECONNREFUSED ::1:27017
```

## Solution Options

### Option 1: Use MongoDB Atlas (Cloud - Recommended for Quick Start)

1. **Go to MongoDB Atlas**: https://www.mongodb.com/cloud/atlas
2. **Create a free account** (if you don't have one)
3. **Create a new cluster** (Free tier is fine)
4. **Get your connection string**:
   - Click "Connect" on your cluster
   - Choose "Connect your application"
   - Copy the connection string (looks like: `mongodb+srv://username:password@cluster.mongodb.net/`)
5. **Update your `.env` file** in the `server` folder:
   ```env
   PORT=5000
   MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/skillswap?retryWrites=true&w=majority
   JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
   ```
   Replace `username`, `password`, and `cluster` with your actual values.

6. **Restart your server**

### Option 2: Install and Run Local MongoDB

#### For Windows:

1. **Download MongoDB**: https://www.mongodb.com/try/download/community
2. **Install MongoDB** (follow the installer)
3. **Start MongoDB Service**:
   - Open Command Prompt as Administrator
   - Run: `net start MongoDB`
   - OR find "MongoDB" in Services and start it

4. **Verify it's running**:
   ```bash
   mongod --version
   ```

5. **Restart your server**

#### For Mac/Linux:

1. **Install MongoDB**:
   ```bash
   # Mac (using Homebrew)
   brew tap mongodb/brew
   brew install mongodb-community
   
   # Start MongoDB
   brew services start mongodb-community
   ```

2. **Restart your server**

## After Fixing MongoDB

1. **Restart your backend server**:
   ```bash
   cd server
   npm run dev
   ```

2. **You should see**:
   ```
   ✅ MongoDB Connected successfully
   🚀 Server running on port 5000
   ```

3. **Try logging in again** - it should work now!

## Quick Test

After starting MongoDB, run this to verify:
```bash
cd server
node check-server.js
```

You should see: `✅ MongoDB connection successful!`

## Still Having Issues?

- Make sure the `.env` file exists in the `server` folder
- Check that MongoDB service is actually running
- For MongoDB Atlas, make sure your IP is whitelisted (0.0.0.0/0 for testing)

