# Restful Booker API - Test Suite

A comprehensive API test suite built with Postman to test the Restful Booker hotel booking API. This project covers happy path testing, negative testing, and boundary testing across all core API endpoints.

## Tools Used
- Postman
- JavaScript (Postman test scripts)
- Restful Booker API (https://restful-booker.herokuapp.com)

## Test Coverage

### Happy Path Tests
- Generate authentication token
- Get all bookings
- Get a specific booking by ID
- Create a new booking
- Update an existing booking
- Delete a booking
- Create and verify a booking (chained request)

### Negative Tests
- Get a non existent booking (ID 99999)
- Authenticate with invalid credentials
- Create a booking with missing required fields
- Update a non existent booking
- Invalid date format in booking
- Negative total price

## Bugs Found

| Bug | Expected | Actual |
|-----|----------|--------|
| Create Booking returns wrong status code | 201 Created | 200 OK |
| Missing required fields | 400 Bad Request | 500 Internal Server Error |
| Invalid date format accepted | 400 Bad Request | 200 OK |
| Inconsistent token authentication | Token auth should work | Basic Auth required instead |
| Delete returns wrong response | 200 or 204 | 201 Created |
| Negative price accepted | 400 Bad Request | 200 OK |
| Bookings not persisting reliably | Booking retrievable after creation | 404 Not Found |

## How to Run
1. Download and install Postman
2. Import the collection file `Restful-Booker-API-Test-Suite.json`
3. Create an environment called `Restful Booker Environment` with a variable called `token`
4. Run the collection starting with the Auth folder to generate a token
5. Run remaining folders in order

## Key Learnings
- Hands on experience testing REST API endpoints using Postman
- Writing automated test scripts in JavaScript
- Identifying and documenting real bugs in an API
- Understanding HTTP status codes and REST best practices
- Using environment variables to manage dynamic data across requests
