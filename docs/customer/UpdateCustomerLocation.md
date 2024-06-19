### Customer Endpoints

### Update Customer Location

**Endpoint**: `POST /api/Customer/UpdateCustomerLocation`

**Description**: Updates the customer's location based on latitude and longitude, when customer update his location you have to call this API, just to infrom the system about the latest location for the customer.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `lat` (double): The latitude of the customer's location (required).
- `lng` (double): The longitude of the customer's location (required).

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (null): No data is returned in the response.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": null
}
