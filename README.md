# FastAPI Assignment 1
## Assignment Description

This assignment demonstrates building basic REST APIs using FastAPI for a simple product management system.

The project includes multiple endpoints for viewing products, filtering products by category, checking available stock, searching products by name, and generating store summary information.

## Implemented APIs
### 1. Products List API

Returns all available products in the store along with the total number of products.

Endpoint:

GET /products

Example Response:
```
{
 "products": [...],
 "total": 7
}
```
### 2. Category Filter API

Returns products that belong to a specific category.

Endpoint:

GET /products/category/{category_name}

Example:
```
/products/category/Electronics
```
If no products are found:
```
{"error": "No products found in this category"}
```
### 3. In-Stock Products API

Displays only the products that are currently available in stock.

Endpoint:

GET /products/instock

Example Response:
```
{
 "in_stock_products": [...],
 "count": 5
}
```
### 4. Store Summary API

Displays an overview of the store including product statistics.

Information included:

Total products

In-stock products

Out-of-stock products

Available product categories

Endpoint:

GET /store/summary
### 5. Product Search API

Allows users to search products using a keyword.
The search is case-insensitive.

Endpoint:

GET /products/search/{keyword}

Example:
```
/products/search/mouse
```
If no products match the search:
```
{"message": "No products matched your search"}
```
### Bonus Feature – Product Deals API

Returns the cheapest product and the most expensive product available in the store.

Endpoint:

GET /products/deals


# FastAPI Assignment 2

## Assignment Description

This assignment demonstrates building REST APIs using **FastAPI**.
The project includes multiple endpoints for product management, filtering, feedback submission, and bulk order processing.

## Implemented APIs

### 1. Product Filter API

Filter products using query parameters such as category, minimum price, and maximum price.

Endpoint:

```
GET /products/filter
```

Example:

```
/products/filter?min_price=400
```
### 2. Product Price API

Fetch only the price and name of a product using its ID.

Endpoint:

```
GET /products/{product_id}/price
```
### 3. Customer Feedback API

Submit product feedback using POST request with validation.

Endpoint:

```
POST /feedback
```

Example Request Body:

```
{
  "customer_name": "Priya",
  "product_id": 1,
  "rating": 5,
  "comment": "Great product"
}
```
### 4. Product Summary Dashboard

Displays statistics about products such as:

* Total products
* In-stock / Out-of-stock
* Most expensive product
* Cheapest product
* Product categories

Endpoint:

```
GET /products/summary
```
### 5. Bulk Order API

Allows companies to place bulk orders with validation and subtotal calculation.

Endpoint:

```
POST /orders/bulk
```

# FastAPI Assignment 3
## Assignment Description

This assignment focuses on building a simple **Product Management API** using FastAPI.
The goal is to practice REST API development, request validation, and response handling using Python and FastAPI.

The API manages a list of products stored in memory and allows users to perform common CRUD operations.

### Objectives

* Understand how to build APIs using FastAPI
* Implement RESTful endpoints
* Use Pydantic models for request validation
* Handle HTTP responses and status codes
* Perform CRUD operations on in-memory data

### Features Implemented

1. **Retrieve all products**

   * Endpoint returns a list of all available products along with the total count.

2. **Retrieve a product by ID**

   * Fetch a single product using its unique identifier.
   * Returns a `404` error if the product does not exist.

3. **Add a new product**

   * Accepts product details through a request body.
   * Prevents duplicate product names.

4. **Update product details**

   * Allows updating the price and stock availability of a product.

5. **Delete a product**

   * Removes a product from the product list using its ID.

6. **Product audit endpoint**

   * Provides analytics such as:

     * Total products
     * Number of products in stock
     * Out-of-stock product names
     * Total inventory value
     * Most expensive product

7. **Bulk discount feature (Bonus)**

   * Applies a percentage discount to all products belonging to a specified category.

### Testing

All endpoints were tested using the **FastAPI Swagger UI** interface.
Screenshots of API responses are included as part of the assignment submission.

Swagger API documentation:

```
http://127.0.0.1:8000/docs
```

## Implemented APIs

### 1. Get All Products

```
GET /products
```

Returns all available products.

### 2. Get Product by ID

```
GET /products/{product_id}
```

Fetch a single product using its ID.

### 3. Add Product

```
POST /products
```

Adds a new product to the list.

### 4. Update Product

```
PUT /products/{product_id}
```

Updates product price or stock status.

### 5. Delete Product

```
DELETE /products/{product_id}
```

Removes a product from the list.

### 6. Product Audit

```
GET /products/audit
```

Provides product statistics including stock information and total value.

### 7. Bulk Discount (Bonus)

```
PUT /products/discount
```

Applies a percentage discount to all products in a given category.
