# 🛍️ Express.js Products API

## 🚀 Overview
This project is a **RESTful API** built with **Express.js** that manages a list of products.  
It includes standard **CRUD operations**, **middleware implementations**, **error handling**, and **advanced features** like filtering, pagination, and search.

---

## 📦 Features
- **CRUD Operations** for products  
- **Custom Middleware** for logging, authentication, and validation  
- **Error Handling** with custom error classes  
- **Advanced Features:** filtering, pagination, search, and statistics

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

### 2️⃣ Install dependencies
```bash
npm install
```

### 3️⃣ Create an `.env` file
Use the provided `.env.example` as a reference:
```
API_KEY=your_secret_key
```

### 4️⃣ Start the server
```bash
node server.js
```

The server runs by default on:
```
http://localhost:3000
```

---

## 📡 API Endpoints

### 🧾 Base URL
```
http://localhost:3000/api/products
```

### 🔹 GET /api/products
Get all products  
Supports:
- **Filtering:** `?category=Electronics`
- **Pagination:** `?page=1&limit=5`
- **Search:** `?search=phone`

Example:
```
GET /api/products?category=Electronics&page=2&limit=3
```

---

### 🔹 GET /api/products/:id
Get a specific product by its ID  
**Example:** `/api/products/1`

---

### 🔹 POST /api/products
Create a new product  
**Headers:**
```
x-api-key: your_secret_key
```
**Body:**
```json
{
  "name": "Smartphone",
  "description": "Latest model with high performance",
  "price": 999.99,
  "category": "Electronics",
  "inStock": true
}
```

---

### 🔹 PUT /api/products/:id
Update an existing product  
**Headers:**
```
x-api-key: your_secret_key
```
**Body:**
```json
{
  "name": "Updated Phone",
  "price": 899.99
}
```

---

### 🔹 DELETE /api/products/:id
Delete a product  
**Headers:**
```
x-api-key: your_secret_key
```

---

### 🔹 GET /api/products/stats
Get statistics (e.g., count of products by category)

---

## 🧩 Middleware Used
- **Logger:** Logs HTTP method, URL, and timestamp  
- **JSON Parser:** Parses JSON bodies  
- **Authentication:** Verifies API key  
- **Validation:** Ensures valid product data before saving  
- **Error Handler:** Handles errors globally with proper status codes  

---

## 🧪 Example Response

**GET /api/products**
```json
[
  {
    "id": "1",
    "name": "Smartphone",
    "description": "Latest model with high performance",
    "price": 999.99,
    "category": "Electronics",
    "inStock": true
  }
]
```

**POST /api/products (Error Example)**
```json
{
  "error": "ValidationError",
  "message": "Product name is required"
}
```

---

## 👨‍💻 Technologies Used
- Node.js
- Express.js
- UUID (for unique product IDs)
- Body-parser
- Dotenv

---


