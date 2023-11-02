# WIN Backend Engineering Interview

## Scenario

Your mission is to build a portion of an order management system. You need to provide a service that allows other systems and teams to obtain information about orders.

## Deliverables

There are two deliverables for this project:

1. An internal web service API for managing orders
2. A test suite to validate the web service and library work as expected

### General

- Please use either **JavaScript/TypeScript or Python**.
- You may use any framework, such as a web framework or test framework, to help you complete the project.
- You may store the data for this system in any database you choose, however we've included a Docker image loaded with Postgres in this repo.
- You may model the data any way you'd like, including adding data beyond the samples provided.

### Web Service

- Your service should implement several endpoints that accept POST, GET, PUT and DELETE requests. Also 1 endpoint that accepts GET all orders.
- Your service should handle edge cases appropriately and return appropriate HTTP status codes.
- Your service should return an error on creation/updating an order within 3 hrs of a pre-existing order.
- Your service should return JSON results.
- Your service should have at least one test.

## Sample Data

Below is some sample data you can use to populate your database. Feel free to extend or modify this data for your project:

Service Records

```json
[
  {
    "id": 123,
    "name": "Inspection"
  },
  {
    "id": 789,
    "name": "Testing"
  },
  {
    "id": 456,
    "name": "Analysis"
  }
]
```

Orders

```json
[
  {
    "id": "223",
    "datetime": "2022-11-01T11:11:11.111Z",
    "totalfee": 100,
    "services": [
        {
        "id": "123",
        }
    ]
  },
  {
    "id": "224",
    "datetime": "2022-11-01T11:11:11.111Z",
    "totalfee": 100,
    "services": [
        {
        "id": "789",
        }
    ]
  },
  {
    "id": "225",
    "datetime": "2022-11-01T11:11:11.111Z",
    "totalfee": 100,
    "services": [
        {
        "id": "456",
        }
    ]
  }
]
```

## Duration

Up to 2 hours.

## Submission
1.  Clone this repo
2.  Create Web Services and tests
3.  Submit a Pull Request (PR)
4.  In the PR, include a README that includes the following:
      - A description of your solution at a high-level, including language used, framework used, roughly how it works, etc.
      - What trade-offs you made
      - Any assumptions you made that affected your solution
      - What you would change if you built this for production
      - Brief instructions on how to setup the environment to run your project
      - What parts of the spec were completed, how much time you spent, and any particular problems you ran into

## Evaluation
We are looking for: 
1. Communication
2. Solution Design
3. Completeness
4. Code clarity / readability





Order Management API
This is a simple API for managing orders. It allows you to perform CRUD operations (Create, Read, Update, Delete) on orders. You can create new orders, retrieve existing orders, update order details, and delete orders.

Table of Contents
1 Installation
2 Usage
3 Endpoints
4 Example Requests
5 Testing
6 Installation
Before using this API, make sure you have Node.js and npm (Node Package Manager) installed on your system. Additionally, you need to set up a MongoDB database and provide the connection string.

Clone the repository:



git clone https://github.com/your-username/order-management-api.git
cd order-management-api
Install dependencies:



npm install
Set up your MongoDB database:

Create a .env file in the project directory.

Add your MongoDB connection string in the .env file:

c

MONGODB_URI=your-mongodb-connection-string
Replace your-mongodb-connection-string with your actual MongoDB connection string.

Start the API server:



npm start
The API will start running on http://localhost:3000 by default.

Usage
This API allows you to perform the following CRUD operations on orders:

Create: Create a new order.
Read: Retrieve existing orders or a specific order.
Update: Update order details.
Delete: Delete an order.
Endpoints
The API provides the following endpoints:

POST /orders: Create a new order.
GET /orders: Retrieve all orders.
GET /orders/:orderId: Retrieve a specific order.
PUT /orders/:orderId: Update order details.
DELETE /orders/:orderId: Delete an order.
Example Requests
Here are some example requests to interact with the API using a tool like curl. You can use API testing tools like Postman or your preferred programming language to make these requests.

Create a new order:



curl -X POST -H "Content-Type: application/json" -d '{"product": "Product Name", "quantity": 5}' http://localhost:3000/orders
Retrieve all orders:



curl http://localhost:3000/orders
Retrieve a specific order (replace :orderId with the actual order ID):



curl http://localhost:3000/orders/:orderId
Update an order (replace :orderId with the actual order ID):



curl -X PUT -H "Content-Type: application/json" -d '{"quantity": 10}' http://localhost:3000/orders/:orderId
Delete an order (replace :orderId with the actual order ID):



curl -X DELETE http://localhost:3000/orders/:orderId
Testing
The API includes tests to ensure its functionality. You can run the tests using the following command:



npm test
Make sure your API server is not running while running tests.

That's it! You now have a fully functional Order Management API. Feel free to customize the API to meet your specific requirements and integrate it with your application.
