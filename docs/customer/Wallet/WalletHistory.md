### Get Wallet Transactions History

**Endpoint**: `POST /api/Customer/Wallet/History`

**Description**: Retrieves the history of wallet transactions.

**Authentication**: Requires Bearer Token Authentication in the header.

**Optional Parameters**:
- `PageIndex` (int): The page number to retrieve.
- `PageSize` (int): The number of transactions to retrieve per page.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): Contains the transaction history and pagination details.
  - `List` (array): An array of transaction objects, where each object contains:
    - `id` (int): The transaction ID.
    - `paid_amount` (float): The amount paid in the transaction.
    - `paid_date` (string): The date and time when the transaction occurred.
    - `expire_date` (string): The expiration date of the transaction, if applicable.
    - `tran_desc` (string): A description of the transaction.
  - `PageNumber` (int): The current page number.
  - `PageSize` (int): The number of transactions per page.
  - `PageCount` (int): The total number of pages available.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": {
        "List": [
            {
                "id": 5734,
                "paid_amount": 35,
                "paid_date": "2024-06-18T22:49:18.73",
                "expire_date": null,
                "tran_desc": "رصيد كاشباك"
            }
        ],
        "PageNumber": 1,
        "PageSize": 12,
        "PageCount": 1
    }
}
```
