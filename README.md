# ECommerce_Store_DB_Model
#### This is a database model for e-commerce store app in diagrams, SQL vs NoSQL

## SQL
<img width="1070" height="618" alt="Untitled" src="https://github.com/user-attachments/assets/cb1873f3-7dd7-4f1c-922b-d4992fb3bbed" />
*E-Commerce Store DB Model In Diagrams (SQL)*

### Relationship Summary
• users ↔ carts → one-to-one

• categories ↔ products → one-to-many

• carts ↔ cartItems → one-to-many

• products ↔ cartItems → many-to-one

• users ↔ orders → one-to-many (a user can place many orders)

• orders ↔ order_items → one-to-many (an order contains many products)

• products ↔ order_items → many-to-one (a product can appear in many orders)

• orders ↔ payments → one-to-one (one order has one payment record)

## NoSQL
### Users collection
```bash
{
  "_id": "u1",
  "username": "john_doe",
  "role": "customer",
  "address": "123 Main St",
  "created_at": "2025-09-10T10:00:00Z",
  "cart": {
    "items": [
      { "product_id": "p1", "quantity": 2 },
      { "product_id": "p3", "quantity": 1 }
    ]
  }
}
```

### Products Collection
```bash
{
  "_id": "p1",
  "title": "T-Shirt",
  "description": "Cotton T-shirt",
  "price": 25,
  "images": ["img1.jpg", "img2.jpg"],
  "stock": 120,
  "category_id": "c1"
}
```

### Categories Collection
```bash
{
  "_id": "c1",
  "name": "Clothing"
}
```

### Orders Collection
```bash
{
  "_id": "o1",
  "user_id": "u1",
  "created_at": "2025-09-10T12:00:00Z",
  "status": "pending",
  "total_amount": 50,
  "items": [
    { "product_id": "p1", "quantity": 2, "price": 25 }
  ],
  "payment": {
    "method": "credit_card",
    "status": "completed",
    "paid_at": "2025-09-10T12:05:00Z"
  }
}
```
