# Inventory and Data Management System

REST API for managing a product catalogue. Built with Node.js, Express, MongoDB (Mongoose) and dotenv.

## Setup
```bash
npm install
cp .env.example .env     # set MONGO_URI
npm start                # http://localhost:5000
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

**Sample body (POST):**
```json
{ "name": "Gel Pen Pack of 15", "sku": "STNY-PN-713", "category": "Stationery", "price": 120, "quantity": 40, "reorderLevel": 20, "supplier": "Cello Pens" }
```

## Postman Output Screenshots

### Create Product (POST)
![Create](screenshots/create.png)

### Get All Products (GET)
![Get All](screenshots/get-all.png)

### Filter / Sort / Pagination
![Query](screenshots/query.png)

### Get Product by ID
![Get One](screenshots/get-one.png)

### Update Product (PUT)
![Update](screenshots/update.png)

### Stock Adjustment (PATCH)
![Stock](screenshots/stock.png)

### Delete Product (DELETE)
![Delete](screenshots/delete.png)

### Low-Stock Report
![Low Stock](screenshots/low-stock.png)

### Category Summary
![Summary](screenshots/summary.png)

### Error Handling (validation / 404 / insufficient stock)
![Errors](screenshots/errors.png)
