## General Endpoints

### New Customer Registration Step 2

**Endpoint**: `POST /api/General/Customers/NewRegistrationStep2`

**Description**: Completes the second step of the new customer registration process.

**Request Parameters**:
- `step1id` (string): The identifier obtained from step 1 of the registration process.
- `smscode` (string): The SMS code sent to the customer for verification.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (string): A JSON Web Token (JWT) containing authentication information upon successful registration.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6IjU3ODc1NTE1MyIsInJvbGUiOiJDdXN0b21lcnMiLCJBZ2VuY3lfSUQiOiIxMDM3NSIsIlVzZXJJZCI6IjIxMzY4IiwibmJmIjoxNzE4NjU3OTk2LCJleHAiOjE3MTg2NjUxOTYsImlhdCI6MTcxODY1Nzk5NiwiaXNzIjoiaHR0cHM6Ly9zYXlhcmF0ZWNoLmNvbS8iLCJhdWQiOiJodHRwczovL3NheWFyYXRlY2guY29tLyJ9.9ruHuFlLJlwzsdpcYPxECnPT5jQHWjQhnXJHJLKIVto"
}
```