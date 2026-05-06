# 🧪 Urban Grocers API Testing (Sprint 4)

This project contains API test cases designed and executed for the Urban Grocers backend system. The focus of this sprint was to validate REST API behavior through structured positive, negative, and boundary testing.

---

## 🎯 Project Objective

The goal of this project was to:

- Design structured API test cases for backend endpoints
- Validate request and response behavior for product-to-kit functionality
- Test fast delivery calculation logic under various input conditions
- Identify system behavior under valid, invalid, and edge-case inputs

---

## 🔍 API Coverage

### 📦 Product-to-Kit Endpoint
- Add products to a kit using valid product IDs and quantities
- Validate error handling for:
  - Missing product IDs
  - Missing quantities
  - Invalid kit IDs
  - Invalid data types (string, decimal, null values)
  - Boundary limits (e.g., max number of products per request)

---

### 🚚 Fast Delivery Calculation Endpoint
- Validate delivery cost calculation based on:
  - product count
  - product weight
  - delivery time
- Test boundary conditions (minimum and maximum limits)
- Validate system response for invalid payloads:
  - missing fields
  - invalid data types
  - negative values
  - empty XML body

---

## 🧪 Test Design Approach

Test cases were created using:

- Equivalence Partitioning
- Boundary Value Analysis
- Negative Testing
- Data Type Validation
- Input Constraint Validation

---

## 📁 Project Structure

```text
urban-grocers-api-tests/
│
├── test_cases/
│ └── urban_grocers_api_test_cases.xlsx
│
└── README.md
```
---

## 📊 Key Observations

- Several invalid input scenarios returned **500 Internal Server Error instead of expected 400 Bad Request**
- This indicates missing or inconsistent backend validation for edge-case inputs
- The system handles valid inputs correctly but lacks robustness for malformed requests

---

## 🧠 Key Skills Demonstrated

- REST API testing fundamentals
- Test case design for backend systems
- Boundary and negative testing strategies
- Validation of request/response structures
- Analytical QA thinking (identifying unexpected system behavior)

---

## 🛠 Tools Used

- Postman (manual API execution)
- Excel (test case documentation)

---

## 🚀 Summary

This project demonstrates structured API test design and execution for a backend system, focusing on validation of business logic, input constraints, and error handling behavior.
```

---
