#DummyAPI Test Suite 

This document outlines negative test scenarios for the public APIs at: https://dummy.restapiexample.com

----

## 1. Employee by Invalid ID

- **Request**: "GET/employee/7777"
- **Purpose**: Fetching employee data using an invalid ID
- **Expected**: "404 Not Found"
- **Actual Result**: "200 OK"
- **DummyAPI - No Validation**

----

## 2. POST Missing field
- **Request**: "POST /create"
- **Body**:
  ''''json
   {
	"name": ""
   }
- **Expected**: "400 Bad Request"
- **Actual**: "200 OK"
- API accepts incomplete input


----

## 3. PUT Updating Invalid ID
- **Request**: "PUT/update/000000
- **Body**: 
  ''''json
    {
    "name": "Invalid",
    "salary": "1000",
    "age": "100"
    }
- **Expected**: "404 Not Found"
- **Actual**: "200 OK"
- Allows updates to invalid record


----

## 4. DEL Invalid Employee ID
- **Request**: "DELETE/delete/123456789
- **Expected**: "404 Not Found"
  **Actual**: "200 OK"
- Deletes Invalid Employee


----

## 5. Del Deleting Same Employee
- **Request**: "DELETE/delete/2"
- **Expected**: "404 Not Found"
- **Actual**: "200 OK"
- No validation

----

## 6. Updating Invalid Employee
- **Request**: "PUT//update/abc"
- **Expected**: "400"
- **Actual**: "200 OK"
- Allows update to invalid employee

