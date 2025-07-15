# GitHub Deploy Setup for 3Dio

## ✅ Setup Type: Single Repository (Frontend + Backend)

### GitHub Repository: [github.com/IAMLORDOLINTON/3dio](https://github.com/IAMLORDOLINTON/3dio)

---

## Step 1: Local Git Setup (✅ Done)
You’ve already created and pushed to the GitHub repo.

---

## Step 2: Deploy Frontend to Vercel
1. Visit: [https://vercel.com/import](https://vercel.com/import)
2. Choose your GitHub account and select the `3dio` repo
3. Configure project:
   - Framework Preset: `Vite`
   - Install Command: `npm install`
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. Click **Deploy**

Once deployed, Vercel will give you a live URL like:
```
https://3dio.vercel.app
```

---

## Step 3: Deploy Backend to Render
1. Visit: [https://render.com](https://render.com)
2. Click **New Web Service** > Connect to GitHub
3. Select the `3dio` repository
4. Fill in settings:
   - Root Directory: `backend`
   - Build Command: `npm install`
   - Start Command: `node server.js`
   - Add Environment Variable: `NODE_ENV=production`
5. Click **Create Web Service**

Render will provide a backend API URL like:
```
https://3dio-backend.onrender.com
```

---

## Step 4: Update Frontend API Calls
In your file `UploadModal.jsx`, change:
```js
await axios.post("http://localhost:5000/upload", formData);
```
To use your live Render backend URL:
```js
await axios.post("https://3dio-backend.onrender.com/upload", formData);
```

---

## ✅ You're Live!
At this point:
- Your Vercel site hosts the frontend
- Your Render service hosts the backend
- File uploads will route through the deployed backend

Next Step: Enable Crypto Payment with Coinbase
Let me know and I’ll integrate the Coinbase Commerce API into your deployed backend + frontend.
