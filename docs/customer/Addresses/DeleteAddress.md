### Delete Address

**Endpoint**: `POST /api/Customer/DeleteAddress`

**Description**: Deletes an existing address for the customer.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (integer): ID of the address to delete.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (null): No data is returned on successful deletion.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": null
}
```