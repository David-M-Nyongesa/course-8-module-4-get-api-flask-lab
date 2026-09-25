# Product Catalog API

A simple RESTful API built with Flask that serves a fictional product catalog. Supports retrieving all products, filtering by category, and looking up a single product by ID.

## Endpoints

| Method | Route                        | Description                              |
|--------|-------------------------------|-------------------------------------------|
| GET    | `/`                            | Welcome message                          |
| GET    | `/products`                    | Returns all products                     |
| GET    | `/products?category=<name>`    | Returns products filtered by category    |
| GET    | `/products/<id>`               | Returns a single product by ID           |

## Setup

```bash
pip install flask
python app.py
```

The app runs on `http://localhost:5000` by default.

## Usage Examples

**Get all products**
```
GET /products
```
```json
[
  {"id": 1, "name": "Laptop", "price": 899.99, "category": "electronics"},
  {"id": 2, "name": "Book", "price": 14.99, "category": "books"},
  {"id": 3, "name": "Desk", "price": 199.99, "category": "furniture"}
]
```

**Filter by category**
```
GET /products?category=books
```
```json
[
  {"id": 2, "name": "Book", "price": 14.99, "category": "books"}
]
```

**Get a single product**
```
GET /products/1
```
```json
{"id": 1, "name": "Laptop", "price": 899.99, "category": "electronics"}
```

**Product not found**
```
GET /products/99
```
```json
{"error": "Product not found"}
```

## Notes

- Category filtering is case-insensitive.
- Responses are formatted with `jsonify()` and use standard status codes (`200` for success, `404` for a missing product).