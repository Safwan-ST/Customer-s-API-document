## General Endpoints

### Post New Customer Registration Step 1

**Endpoint**: `POST /api/General/Customers/NewRegistrationStep1`

**Description**: Initiates the first step of the new customer registration process.

**Request Parameters**:
- `name` (string): The name of the customer.
- `pwd` (string): The password for the customer, currently passed as the name without spaces.
- `email` (string): The email address of the customer.
- `mobile` (string): The mobile number of the customer.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object|null): Contains additional data if the operation is successful, otherwise `null`.
  - `id_step2` (int): Identifier for the next registration step (only in successful response).
  - `smscode` (string): The SMS code sent to the customer for verification (only in successful response).

**Response Example (Customer Already Exists)**:
```json
{
  "status": false,
  "message": "رقم الجوال غير متاح",
  "error": "",
  "Data": null
}
```

**Response Example (Successfull Registeration)**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "id_step2": 14847,
    "smscode": "6540"
  }
}
```
