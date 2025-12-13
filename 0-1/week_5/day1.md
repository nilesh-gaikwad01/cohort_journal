# Week 5 – Day 1: MongoDB Setup & Basics (Learn in Public)

## 📌 Topics Covered Today
- Installing MongoDB & MongoDB Compass
- Understanding NoSQL database structure
- Connecting Node.js backend with MongoDB using Mongoose
- Creating project folder structure for backend + database
- Creating first Mongoose schema/model
- Testing database connection

---

## 🔹 1. Installing MongoDB & MongoDB Compass

Today I installed:
- **MongoDB Community Server** → database engine  
- **MongoDB Compass** → GUI tool to view databases & collections  

Compass helped me visually understand:
- Databases  
- Collections  
- Documents  

---

## 🔹 2. Understanding the Basics of MongoDB

MongoDB is a **NoSQL document database**, which means:

| SQL Term     | MongoDB Term  |
|--------------|----------------|
| Database     | Database       |
| Table        | Collection     |
| Row/Record   | Document       |

### A document looks like this:
```json
{
  "name": "Nilesh",
  "email": "test@example.com",
  "age": 21
}
MongoDB stores data in flexible JSON-like objects.

🔹 3. Connecting Node.js to MongoDB (Using Mongoose)
Install Mongoose:
bash
Copy code
npm install mongoose
Create a connection file:
javascript
Copy code
const mongoose = require("mongoose");

mongoose
  .connect("mongodb://127.0.0.1:27017/week5db")
  .then(() => console.log("MongoDB Connected"))
  .catch((err) => console.log("DB Error:", err));
This creates a local database called week5db.

🔹 4. Project Folder Structure
bash
Copy code
project/
│── app.js
│── /config
│     └── db.js
│── /models
│     └── User.js
│── /routes
│     └── userRoutes.js
│── package.json
This structure helps keep backend files clean & scalable.

🔹 5. Creating First Mongoose Schema (User Model)
javascript
Copy code
const mongoose = require("mongoose");

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  age: Number
});

module.exports = mongoose.model("User", userSchema);
This automatically creates a users collection.

🔹 6. Testing the Database Connection
javascript
Copy code
node app.js
Output:

arduino
Copy code
MongoDB Connected
Server running...
MongoDB Compass also showed my new database → week5db

🔹 7. Practice Completed Today
Installed & configured MongoDB

Installed MongoDB Compass

Connected backend using Mongoose

Created a proper backend folder structure

Built first schema/model

Tested connection successfully

