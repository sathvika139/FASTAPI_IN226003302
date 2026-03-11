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
