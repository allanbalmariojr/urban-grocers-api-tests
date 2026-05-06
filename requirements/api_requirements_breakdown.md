## 📋 API Requirements Breakdown – Urban Grocers

This document breaks down functional requirements into testable conditions used to design API test cases for the Urban Grocers backend system.

---

### 📦 Requirement 1: Working with Kits
Endpoint

POST /api/v1/kits/:id/products

Functional Rules
Users can add existing products to a kit
Request body contains productsList array
Each item includes:
id (product ID)
quantity
Business Logic Constraints
productsList.length ≤ 30
Length is based on unique product IDs, not total quantity
Duplicate product IDs are not counted as separate entries
Validation Rules
Condition	Expected Response
Valid product IDs + valid kit ID	200 OK
Product ID does not exist	400 Bad Request
Kit ID does not exist	404 Not Found
Invalid request body structure	400 Bad Request
productsList length > 30 unique items	400 Bad Request
🚚 Requirement 2: Working with Deliveries
Endpoint

/fast-delivery/v3.1.1/calculate-delivery.xml

Functional Rules
Fast Delivery is available only when shipping calculation rules are satisfied
Request must follow XML structure defined in API documentation
Validation Focus Areas
Required XML fields must be present
Data types must match specification
Invalid or missing fields should be rejected
Expected Behavior
Condition	Expected Response
Valid XML payload	Successful calculation
Missing required fields	Error response
Invalid data types	Error response
Malformed XML	Error response
🧠 Notes for Test Design

These requirements were used to design:

Positive test cases
Negative test cases
Boundary tests (e.g., productsList limit = 30)
Input validation tests
Error handling verification
