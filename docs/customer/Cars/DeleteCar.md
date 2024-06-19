### Delete a Car

**Endpoint**: `POST /api/Customer/DeleteCar`

**Description**: Deletes an existing car from the customer's profile.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (int, required): The ID of the car to be deleted.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (null): No additional data is returned.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": null
}
```
