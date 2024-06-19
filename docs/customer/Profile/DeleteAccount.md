### Delete Account

**Endpoint**: `POST /api/Customer/DeleteAcccount`

**Description**: Deletes the customer account associated with the provided bearer token in the header. This action is irreversible.

**Authentication**: Requires Bearer Token Authentication in the header.

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

