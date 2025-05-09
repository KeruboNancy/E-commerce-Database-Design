# 🛍️ E-Commerce Database Schema

## 📘 Overview

This project defines a robust and scalable relational database schema for an e-commerce platform. It covers core entities such as products, brands, categories, product variations, sizes, colors, attributes, and inventory management.

The schema is designed to support features such as:

- Product listings with rich variations (e.g., size, color)
- Flexible product attributes
- Inventory tracking
- Organized product categories and branding

---

## 🗺️ ER Diagram

![E-Commerce Database ER Diagram](/eccomerce.png)

> _Diagram generated using [dbdiagram.io](https://dbdiagram.io)_

---

## 🧩 Database Tables

### 🔹 `product_category`

- `category_id` (PK): Unique identifier.
- `name`: Name of the category.
- `description`: Description of the category.

### 🔹 `brand`

- `brand_id` (PK): Unique identifier.
- `name`: Brand name.
- `description`: Brand details.

### 🔹 `product`

- `product_id` (PK): Unique product ID.
- `name`: Product name.
- `brand_id`: FK to `brand`.
- `category_id`: FK to `product_category`.
- `base_price`: Base price before overrides.
- `description`: Product description.

### 🔹 `color`

- `color_id` (PK): Unique ID for each color.
- `name`: Color name.
- `hex_value`: Hexadecimal color code.

### 🔹 `size_category`

- `size_category_id` (PK): ID for size groups (e.g., shoe sizes, clothing).
- `name`: Size category name.

### 🔹 `size_option`

- `size_option_id` (PK): Size option ID.
- `value`: Size value (e.g., "M", "42").
- `size_category_id`: FK to `size_category`.

### 🔹 `product_variation`

- `variation_id` (PK): Unique ID per variation.
- `color_id`: FK to `color`.
- `size_option_id`: FK to `size_option`.

### 🔹 `product_item`

- `product_item_id` (PK): Unique ID per inventory item.
- `product_id`: FK to `product`.
- `variation_id`: FK to `product_variation`.
- `stock_quantity`: Quantity available in stock.
- `price_override`: Optional price adjustment.

### 🔹 `product_image`

- `image_id` (PK): Unique ID.
- `product_item_id`: FK to `product_item`.
- `image_url`: URL/path to the image.

### 🔹 `attribute_category`

- `attribute_category_id` (PK): Unique ID.
- `name`: Category name for organizing attributes.

### 🔹 `attribute_type`

- `attribute_type_id` (PK): Unique ID.
- `name`: Attribute name (e.g., material).
- `data_type`: Data type (e.g., string, number).
- `attribute_category_id`: FK to `attribute_category`.

### 🔹 `product_attribute`

- `attribute_id` (PK): Unique ID.
- `product_id`: FK to `product`.
- `attribute_type_id`: FK to `attribute_type`.
- `value`: Actual attribute value (e.g., “Cotton”, “13 inches”).

---

## 🚀 Tools Used

- **DB Diagram**: [dbdiagram.io](https://dbdiagram.io) for schema visualization
- **Markdown**: For documentation
- **SQL**: Schema creation and modeling

---

## 💬 How to Use

1. Clone the repository.
2. Run the SQL script in your preferred RDBMS (MySQL/PostgreSQL/etc).
3. Use this schema as a base for your e-commerce backend development.

---

## 📸 Author & Acknowledgment

Prepared as part of a group assignment on E-Commerce system design.  
Special thanks to the tools and communities helping visualize and structure databases.
