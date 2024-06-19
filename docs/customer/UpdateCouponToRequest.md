### 6. Update Request with Coupon Code

**Endpoint**: `POST /api/Customer/UpdateCouponToRequest`

**Description**: Updates a request with a coupon code if no coupon has been added before the request was created.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (int): (required) The order ID.
- `coupon_name` (string): (required) The coupon code.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (null): No data is returned.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": null
}
```