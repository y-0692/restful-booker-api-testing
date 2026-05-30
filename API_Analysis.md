# Restful Booker API Testing - API Analysis

## Project Overview

This project demonstrates end-to-end REST API testing of the Restful Booker application using Postman.

The objective is to validate authentication, booking management functionality, response data, status codes, and error handling through both positive and negative test scenarios.

---

## API Endpoints

| Method | Endpoint      | Description                   |
| ------ | ------------- | ----------------------------- |
| POST   | /auth         | Generate authentication token |
| POST   | /booking      | Create a new booking          |
| GET    | /booking/{id} | Retrieve booking details      |
| PUT    | /booking/{id} | Update an existing booking    |
| DELETE | /booking/{id} | Delete a booking              |

---

## Authentication

Authentication is required for:

* Update Booking
* Delete Booking

### Authentication Endpoint

POST /auth

### Request Body

```json
{
  "username": "admin",
  "password": "password123"
}
```

### Expected Response

```json
{
  "token": "generated_token"
}
```

---

## Booking Data Structure

### Request Fields

| Field                 | Type    | Required |
| --------------------- | ------- | -------- |
| firstname             | String  | Yes      |
| lastname              | String  | Yes      |
| totalprice            | Number  | Yes      |
| depositpaid           | Boolean | Yes      |
| bookingdates.checkin  | Date    | Yes      |
| bookingdates.checkout | Date    | Yes      |
| additionalneeds       | String  | No       |

### Sample Request

```json
{
  "firstname": "Nang",
  "lastname": "Khay",
  "totalprice": 5000,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2026-01-01",
    "checkout": "2027-01-01"
  },
  "additionalneeds": "Clean and comfy"
}
```

---

## APIs Tested

### Authentication

* Generate Token

### Booking

* Create Booking
* Get Booking
* Update Booking
* Delete Booking

---

## Test Coverage

### Positive Test Cases

#### Authentication

* Generate authentication token successfully
* Verify token exists in response
* Verify response status code is 200

#### Create Booking

* Create booking successfully
* Verify booking ID is generated
* Verify booking ID data type
* Verify request data matches response data

#### Get Booking

* Retrieve booking successfully
* Verify returned booking information

#### Update Booking

* Update booking successfully using valid token
* Verify updated values are returned

#### Delete Booking

* Delete booking successfully using valid token
* Verify booking is removed

---

### Negative Test Cases

#### Authentication

* Invalid username
* Invalid password
* Missing credentials

#### Create Booking

* Missing firstname
* Missing lastname
* Invalid data types
* Empty request body

#### Update Booking

* Update booking without token
* Update booking with invalid token

#### Delete Booking

* Delete booking without token
* Delete booking with invalid token

---

## Validation Performed

### Response Validation

* Status code validation
* Response body validation
* JSON schema validation
* Required field validation
* Data type validation

### Authentication Validation

* Token generation validation
* Token existence validation

### Booking Validation

* Booking ID validation
* Booking data validation
* Updated data validation

---

## Postman Variables

| Variable  | Purpose                     |
| --------- | --------------------------- |
| token     | Stores authentication token |
| bookingId | Stores generated booking ID |

### Example

```javascript
pm.collectionVariables.set("token", jsonData.token);
pm.collectionVariables.set("bookingId", jsonData.bookingid);
```

---

## Tools Used

* Postman
* REST API
* JSON
* GitHub

---

## Repository Structure

```text
restful-booker-api-testing
│
├── README.md
├── API_Analysis.md
├── Restful Booker API Testing.postman_collection.json
└── LICENSE
```

---

## Key Learning Outcomes

* REST API testing fundamentals
* Authentication handling
* CRUD operation testing
* Positive and negative test design
* Response validation using Postman scripts
* Collection variable management
* API documentation
* GitHub project management

---

## Conclusion

This project demonstrates practical REST API testing using Postman. The scope includes authentication testing, CRUD operations, positive and negative test scenarios, response validation, and collection variable management. The project showcases QA testing skills and provides a foundation for future API automation using Newman and CI/CD integration.
