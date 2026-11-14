# Inventory and Data Management System

REST API for managing a product catalogue. Built with Node.js, Express, MongoDB (Mongoose) and dotenv.

## Setup
```bash
npm install
cp .env.example .env     # set MONGO_URI
npm run dev              # http://localhost:5000
```

## Endpoints
| Method | URL | Description |
|---|---|---|
| POST | `/api/products` | Create product |
| GET | `/api/products` | List with filter, sort, pagination |
| GET | `/api/products/:id` | Get one product |
| PUT | `/api/products/:id` | Update product details |
| PATCH | `/api/products/:id/stock` | Restock / sale, body `{ "change": 10 }` |
| DELETE | `/api/products/:id` | Delete product |
| GET | `/api/products/low-stock` | Items with quantity <= reorderLevel |
| GET | `/api/products/summary` | Category-wise summary (aggregation) |

**Query params for GET /api/products:** `category`, `supplier`, `search`, `minPrice`, `maxPrice`, `inStock`, `sort` (e.g. `-price,name`), `page`, `limit`.

## Postman Output Screenshots

### 1. Create Product (POST `/api/products`)
![Create Product](screenshots/create.png)

### 2. Get All Products (GET `/api/products`)
![Get All Products](screenshots/get-all.png)

### 3. Update Product (PUT `/api/products/:id`)
![Update Product](screenshots/update.png)

### 4. Stock Adjustment (PATCH `/api/products/:id/stock`)
![Stock Adjustment](screenshots/stock.png)

### 5. Delete Product (DELETE `/api/products/:id`)
![Delete Product](screenshots/delete.png)

### 6. Low-Stock Report (GET `/api/products/low-stock`)
![Low Stock Report](screenshots/low-stock.png)

### 7. Category Summary (GET `/api/products/summary`)
![Category Summary](screenshots/summary.png)

### 8. Error Handling - Route Not Found (404)
![Not Found](screenshots/not-found.png)
