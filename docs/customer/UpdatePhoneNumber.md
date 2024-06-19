### Customer Endpoints

### Update Customer Cellphone Number - Step 1

**Endpoint**: `POST /api/Customer/Profile/Mobile/UpdateStep1`

**Description**: Initiates the process of updating the customer's cellphone number.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `mob` (string): (required) The phone number without the country code (966).

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `id` (int): The identifier for the next step in the process.
- `message` (string): A message describing the result of the operation.

**Response example**:
```json
{
"status": true,
"id": 14848,
"message": "تمت العمليه بنجاح"
}
```

### Update Customer Cellphone Number - Step 2

**Endpoint**: `POST /api/Customer/Profile/Mobile/UpdateStep2`

**Description**: Completes the process of updating the customer's cellphone number.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (int): (required) The identifier from the first step.
- `smscode` (string): (required) The SMS code received by the customer.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `mob` (string): The updated phone number including the country code (966).
- `message` (string): A message describing the result of the operation.

**Response example**:
```json
{
"status": true,
"mob": "966551730349",
"message": "تمت العمليه بنجاح"
}
```