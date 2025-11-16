# 📝 Postify

A **minimal social media web app** built with **Node.js**, **Express**, **MongoDB**, **EJS**, and **TailwindCSS**.  
Users can register, log in, create posts, like/unlike, edit, upload profile pictures, and manage their profile — all with **JWT-based authentication**.
 
---
 
## 🚀 Features 

### 👤 Authentication
- Secure user registration and login with **bcrypt** password hashing  
- **JWT-based authentication** with cookies for persistent sessions  
- Custom `isLoggedIn` middleware for route protection  
- Logout feature to clear user sessions  
 
### 🖼️ Profile Picture Upload
- Users can upload or change their **profile picture**  
- Uploads handled using **Multer** and stored in `public/images/uploads/`  
- File names are randomly generated using **crypto** for uniqueness  
- Profile pictures displayed dynamically on user profiles  

### 💬 Posts
- Create new posts directly from your profile  
- View all your posts in a clean, minimal feed  
- Like or unlike posts instantly  
- Edit post content anytime  
- (Optional) Delete post support — easy to add  

### 🖥️ Frontend
- Server-side rendering using **EJS** templates  
- Styled with **TailwindCSS**  
- Clean, minimal, and responsive **dark UI**  

---

## 🧠 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | EJS + TailwindCSS |
| **Backend** | Node.js + Express.js |
| **Database** | MongoDB + Mongoose |
| **Authentication** | JWT + bcrypt |
| **Templating** | EJS |
| **File Uploads** | Multer + crypto |

---

## 📁 Folder Structure

Postify/
│
├── models/
│ ├── user.js # User schema & model
│ └── post.js # Post schema & model
│
├── views/
│ ├── index.ejs # Register page
│ ├── login.ejs # Login page
│ ├── profile.ejs # User profile & posts
│ ├── profileupload.ejs # Profile picture upload page
│ └── edit.ejs # Edit post form
│
├── config/
│ └── multerconfig.js # Multer setup for file uploads
│
├── public/
│ └── images/uploads/ # Uploaded profile pictures
│
├── app.js # Main Express app (routes & middleware)
├── package.json
└── .gitignore

yaml
Copy code

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/<your-username>/Postify.git
cd Postify
2️⃣ Install dependencies
bash
Copy code
npm install
3️⃣ Create a .env file (recommended)
Add your environment variables:

ini
Copy code
MONGODB_URI=mongodb://127.0.0.1:27017/miniproject
JWT_SECRET=helllllooooo
PORT=3000
💡 In the current code, some values are hardcoded. Move them into .env for better security.

4️⃣ Run the app
bash
Copy code
node app.js
or, using nodemon:

bash
Copy code
npx nodemon app.js
5️⃣ Visit the app
Open your browser and go to:
👉 http://localhost:3000

🧩 How It Works
🔐 Registration
Passwords are hashed using bcrypt

A JWT token is generated and stored in cookies

🔑 Login
Validates credentials and issues a new JWT token

Maintains secure session using cookies

👤 Profile
Displays user info and their posts

Allows profile picture uploads using Multer

Upload route:

bash
Copy code
POST /upload
Accepts a single file field named "image"

❤️ Likes
GET /like/:id toggles the current user’s like status for a post

✏️ Edit
GET /edit/:id loads the edit form

POST /update/:id saves changes

🚪 Logout
Clears the JWT cookie

Redirects back to login

🔒 Security Highlights
bcrypt for secure password hashing

JWT for authentication & session management

isLoggedIn middleware protects private routes

Cookies used for storing tokens (not localStorage)

crypto.randomBytes() generates unique filenames for uploads

🧰 Dependencies
Package	Purpose
express	Web framework
mongoose	MongoDB ODM
bcrypt	Password hashing
jsonwebtoken	JWT authentication
cookie-parser	Cookie handling
multer	File uploads
crypto	Generate unique filenames
ejs	Template engine
tailwindcss	CSS framework
