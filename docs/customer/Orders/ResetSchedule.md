### Reset Order Request Schedule

**Endpoint**: `POST /api/Customer/Orders/ResetRequestSchedule`

**Description**: Resets the schedule for an existing order request.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (integer, required): The ID of the order request to reschedule.
- `date` (string, required): The new date for the booking in `YYYY-MM-DD` format.
- `hour` (integer, required): The new hour for the booking (24-hour format).
- `minutes` (integer, optional): The new minutes for the booking.

**Request Example**:
https://satc.live/api/Customer/Orders/ResetRequestSchedule?id=16968&date=2024-06-23&hour=23&minutes=15

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (null): No data returned for this operation.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": null
}
```