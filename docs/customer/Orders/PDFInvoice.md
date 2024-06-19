### Get Paid Booking Orders Invoice as PDF

**Endpoint**: `GET /api/Customer/Orders/PDFInvoice`

**Description**: Retrieves the invoice for a paid booking order in PDF format as binary data.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (integer, required): The order ID for which the invoice is being requested.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (string): The PDF invoice as a base64-encoded string.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": "JVBERi0xLj..." //binary data
}
```
