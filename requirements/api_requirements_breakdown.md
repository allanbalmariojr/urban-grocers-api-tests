# 📋 API Requirements Breakdown – Urban Grocers

This document breaks down functional requirements into testable conditions used to design API test cases for the Urban Grocers backend system.

---

## 📦 Requirement 1: Working with Kits

### Endpoint
`POST /api/v1/kits/:id/products`

### Functional Behavior
- Users should be able to add existing products to a kit.
- The request body contains a `productsList` array.
- Each item in `productsList` includes:
  - `id` (product ID)
  - `quantity`

### Business Logic Rules
- The maximum allowed length of `productsList` is **30 unique product IDs**.
- The list length is based on **unique product IDs**, not total quantity.
  - Example: multiple quantities of the same product still count as 1 entry per unique ID.

### Example Request Body
```json
{
  "productsList": [
    {
      "id": 1,
      "quantity": 2
    },
    {
      "id": 6,
      "quantity": 2
    }
  ]
}
```
### Validation Rules
| Condition | Expected Response |
|----------|------------------|
| Valid product IDs and valid kit ID | 200 OK |
| Non-existent product ID | 400 Bad Request |
| Non-existent kit ID | 404 Not Found |
| Invalid request body structure | 400 Bad Request |
| productsList length > 30 unique products | 400 Bad Request |

---

## 🚚 Requirement 2: Working with Deliveries
### Endpoint

`/fast-delivery/v3.1.1/calculate-delivery.xml`

### Functional Behavior
The Fast Delivery service calculates delivery cost based on shipping rules.
The request must follow the XML structure defined in the API documentation.

### Validation Focus Areas
Required XML fields must be present
Data types must match specification
Input must follow correct structure and format

### Expected Behavior
| Condition | Expected Response |
|----------|------------------|
| Valid XML payload | Successful delivery calculation |
| Missing required fields | Error response |
| Invalid data types | Error response |
| Empty or malformed XML body | Error response |

---

## 🧠 How These Requirements Were Used

These requirements were translated into structured API test cases covering:

Positive testing (valid inputs)
Negative testing (invalid inputs)
Boundary testing (e.g., productsList limit = 30)
Data validation testing
Error handling verification (status codes and response structure)

---

## 📊 Test Coverage Summary
| Requirement Area | Test Type Coverage | Focus |
|------------------|-------------------|------|
| Kit Products API | Positive / Negative / Boundary | Input validation, business rules |
| Delivery Calculation API | Validation / Error Handling | XML structure, required fields |

---

## 🚀 Summary

This document serves as the foundation for API test case design in the Urban Grocers project. It ensures test coverage is directly traceable to functional requirements and validates both business logic and system error handling behavior.

---
