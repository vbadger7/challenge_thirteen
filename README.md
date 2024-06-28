# E-commerce Back-End

This is the back-end for an e-commerce application. It is built using Node.js, Express.js, Sequelize, and PostgreSQL. The application provides a RESTful API for managing categories, products, and tags in an e-commerce setting.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
  - [Categories](#categories)
  - [Products](#products)
  - [Tags](#tags)
- [Testing with Insomnia](#testing-with-insomnia)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/e-commerce-back-end.git
    cd e-commerce-back-end/Develop
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Create a `.env` file in the `Develop` directory and add the following environment variables:
    ```env
    DB_NAME='ecommerce_db'
    DB_USER='your-username'
    DB_PASSWORD='your-password'
    ```

4. Create the PostgreSQL database and user (if not already created):
    ```sql
    CREATE DATABASE ecommerce_db;
    CREATE USER your-username WITH PASSWORD 'your-password';
    GRANT ALL PRIVILEGES ON DATABASE ecommerce_db TO your-username;
    ```

5. Seed the database:
    ```bash
    npm run seed
    ```

## Usage

1. Start the server:
    ```bash
    npm start
    ```

2. The server will be running on `http://localhost:3001`.

## API Endpoints

### Categories

- **GET /api/categories**: Get all categories
- **GET /api/categories/:id**: Get a single category by ID
- **POST /api/categories**: Create a new category
  - Body:
    ```json
    {
      "category_name": "Accessories"
    }
    ```
- **PUT /api/categories/:id**: Update a category by ID
  - Body:
    ```json
    {
      "category_name": "Updated Accessories"
    }
    ```
- **DELETE /api/categories/:id**: Delete a category by ID

### Products

- **GET /api/products**: Get all products
- **GET /api/products/:id**: Get a single product by ID
- **POST /api/products**: Create a new product
  - Body:
    ```json
    {
      "product_name": "New Product",
      "price": 29.99,
      "stock": 20,
      "category_id": 1
    }
    ```
- **PUT /api/products/:id**: Update a product by ID
  - Body:
    ```json
    {
      "product_name": "Updated Product",
      "price": 39.99,
      "stock": 15,
      "category_id": 1
    }
    ```
- **DELETE /api/products/:id**: Delete a product by ID

### Tags

- **GET /api/tags**: Get all tags
- **GET /api/tags/:id**: Get a single tag by ID
- **POST /api/tags**: Create a new tag
  - Body:
    ```json
    {
      "tag_name": "new tag"
    }
    ```
- **PUT /api/tags/:id**: Update a tag by ID
  - Body:
    ```json
    {
      "tag_name": "updated tag"
    }
    ```
- **DELETE /api/tags/:id**: Delete a tag by ID

## Testing with Insomnia

### Step 1: Install Insomnia

1. Download and install Insomnia from [Insomnia's official website](https://insomnia.rest/download).

### Step 2: Set Up Your Environment

1. Open Insomnia.
2. Create a new workspace by clicking on the dropdown arrow next to the workspace name at the top left and selecting "Create Workspace".
3. Name your workspace and choose the environment (REST, GraphQL, etc.).

### Step 3: Test the `/api/categories` Endpoint

#### GET all categories

1. Click on the "New Request" button.
2. Name your request (e.g., "Get All Categories") and choose the "GET" method.
3. Set the URL to `http://localhost:3001/api/categories`.
4. Click "Send" to make the request and check the response.

#### GET category by ID

1. Click on the "New Request" button.
2. Name your request (e.g., "Get Category by ID") and choose the "GET" method.
3. Set the URL to `http://localhost:3001/api/categories/:id` (replace `:id` with an actual category ID, e.g., `http://localhost:3001/api/categories/1`).
4. Click "Send" to make the request and check the response.

#### POST create a new category

1. Click on the "New Request" button.
2. Name your request (e.g., "Create Category") and choose the "POST" method.
3. Set the URL to `http://localhost:3001/api/categories`.
4. In the "Body" tab, choose "JSON" and add a new category object, e.g.:
    ```json
    {
      "category_name": "Accessories"
    }
    ```
5. Click "Send" to make the request and check the response.

#### PUT update a category by ID

1. Click on the "New Request" button.
2. Name your request (e.g., "Update Category by ID") and choose the "PUT" method.
3. Set the URL to `http://localhost:3001/api/categories/:id` (replace `:id` with an actual category ID, e.g., `http://localhost:3001/api/categories/1`).
4. In the "Body" tab, choose "JSON" and add the updated category object, e.g.:
    ```json
    {
      "category_name": "Updated Accessories"
    }
    ```
5. Click "Send" to make the request and check the response.

#### DELETE a category by ID

1. Click on the "New Request" button.
2. Name your request (e.g., "Delete Category by ID") and choose the "DELETE" method.
3. Set the URL to `http://localhost:3001/api/categories/:id` (replace `:id` with an actual category ID, e.g., `http://localhost:3001/api/categories/1`).
4. Click "Send" to make the request and check the response.

### Step 4: Test the `/api/products` Endpoint

Follow the same steps as for the categories endpoint but use the URL `http://localhost:3001/api/products`.

### Step 5: Test the `/api/tags` Endpoint

Follow the same steps as for the categories endpoint but use the URL `http://localhost:3001/api/tags`.

### Step 6: Check Responses

1. Check the responses for each request to ensure they are as expected.
2. For successful requests, you should get a `200 OK` status code and the corresponding JSON response.
3. For invalid requests (e.g., a non-existent ID), you should get a `404 Not Found` status code and a relevant error message.

### Step 7: Verify CRUD Operations

1. Make sure you can create, read, update, and delete categories, products, and tags.
2. Verify the database is updated accordingly after each operation.

By following these steps, you can thoroughly test your API endpoints using Insomnia. If you encounter any errors, check your server logs and ensure your database is properly configured and running.
