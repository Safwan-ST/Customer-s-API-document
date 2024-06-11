## Authentication Endpoints

### 1. Authenticate By SMS Step 1

**Endpoint**: `POST /api/Auth/Token/AuthenticateBySMSStep1`

**Description**: This is the first step to sign in. It receives the phone number and sends an SMS code to the user.

**Request URL Example**:
https://satc.live/api/Auth/Token/AuthenticateBySMSStep1?mobileno=966548093416

**Request Parameters**:
- `mobileno` (string): The mobile number of the user.
  - **Example**: `966548093416`

**Response Example**:
```json
{
    "status": true,
    "message": "Operation Done Successfully",
    "error": "",
    "Data": {
        "id_step2": 14817,
        "smscode": "3026"
    }
}
```
**Response Parameters**:

- `status` (boolean): Indicates whether the operation was successful.

- `message` (string): A message describing the result of the operation.

- `error` (string): An error message if the operation failed.

- `Data` (object): An object containing the following fields:

  - `id_step2` (string): The identifier for the second step of authentication.
  - `smscode` (string): The SMS code sent to the user's mobile number.
