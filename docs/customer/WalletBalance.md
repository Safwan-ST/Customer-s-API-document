### Get Wallet Balance

**Endpoint**: `POST /api/Customer/Wallet/Balance`

**Description**: Retrieves the customer's wallet balance.

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): Contains the wallet balance.
  - `balance` (int): The balance in the customer's wallet.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": {
        "balance": 0
    }
}
```
