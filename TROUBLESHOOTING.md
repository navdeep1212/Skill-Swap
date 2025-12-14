# Troubleshooting Login/Registration Issues

## Common Issues and Solutions

### Issue: "Registration failed" or "Login failed" even with correct credentials

### Solution 1: Check if Backend Server is Running

**The most common issue is that the backend server is not running.**

1. Open a terminal/command prompt
2. Navigate to the server directory:
   ```bash
   cd server
   ```
3. Start the server:
   ```bash
   npm run dev
   ```
   OR
   ```bash
   node index.js
   ```
4. You should see:
   ```
   MongoDB Connected
   Server running on port 5000
   ```

### Solution 2: Check MongoDB Connection

1. Make sure MongoDB is installed and running
2. For local MongoDB:
   ```bash
   mongod
   ```
3. For MongoDB Atlas, check your connection string in `server/.env`

### Solution 3: Verify Environment Variables

Create `server/.env` file with:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/skillswap
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
```

### Solution 4: Check Browser Console

1. Open browser Developer Tools (F12)
2. Go to Console tab
3. Look for error messages when trying to login
4. Common errors:
   - `ECONNREFUSED` - Backend server not running
   - `Network Error` - Cannot reach backend
   - `CORS error` - Backend CORS not configured

### Solution 5: Verify API URL

The frontend should connect to: `http://localhost:5000/api`

Check in browser Network tab:
1. Open Developer Tools (F12)
2. Go to Network tab
3. Try to login
4. Look for the request to `/auth/login`
5. Check if it's going to the correct URL

### Solution 6: Test Backend Directly

Test if the backend is working:

```bash
# Test register endpoint
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"name":"Test User","email":"test@test.com","password":"test123"}'

# Test login endpoint
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"test@test.com","password":"test123"}'
```

### Solution 7: Clear Browser Cache

1. Clear browser cache and cookies
2. Clear localStorage:
   - Open Developer Tools (F12)
   - Go to Application tab
   - Clear Local Storage
   - Try login again

### Solution 8: Check Port Conflicts

If port 5000 is already in use:

1. Change PORT in `server/.env` to another port (e.g., 5001)
2. Update `client/src/context/AuthContext.js`:
   ```javascript
   const API_URL = process.env.REACT_APP_API_URL || 'http://localhost:5001/api';
   ```

## Quick Diagnostic Steps

1. ✅ Is the backend server running? (Check terminal for "Server running on port 5000")
2. ✅ Is MongoDB running? (Check terminal for "MongoDB Connected")
3. ✅ Is the `.env` file created in the server folder?
4. ✅ Are both frontend and backend running?
5. ✅ Check browser console for errors
6. ✅ Check browser Network tab for failed requests

## Still Having Issues?

1. Check the terminal where the backend is running for error messages
2. Check the browser console for detailed error messages
3. Verify all dependencies are installed: `npm install` in both client and server folders

