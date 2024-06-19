### Reject Request

**Endpoint**: `POST /api/Customer/Orders/RejectRequest`

**Description**: Rejects the fixing offer provided to the customer.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Query Parameters**:
- `id` (required): The ID of the request for fixing the car.
- `reason` (required): Reason for rejecting the offer.
- `reason_id` (required): ID of the reason for rejecting the offer.

**Request Query Example**:
https://satc.live/api/Customer/Orders/RejectRequest?id=16970&reason=Rejected_from_app&reason_id=7

**Request Body Parameters**:
- `request_id` (required): The ID of the request for fixing the car.
- `paid_amount` (required): The amount paid by the customer for the service.
- `payment_option_id` (required): The ID of the payment option chosen by the customer.
- `couponid` (optional): ID of the coupon used for payment, if any.

**Request Body Example**:
```json
{
    "request_id": 16970,
    "paid_amount": 300,
    "payment_option_id": 2,
    "couponid": null
}
```

**Response Parameters**:
- `status`: Indicates if the operation was successful (`true` or `false`).
- `message`: Describes the outcome of the operation.
- `error`: Provides details of any errors encountered during the operation.
- `Data`: Contains additional data related to the operation.
  - `totaltopay`: Total amount to be paid after rejecting the request.
  - `mywallet`: Amount in the customer's wallet after the transaction.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": {
        "totaltopay": 300,
        "mywallet": 0
    }
}
```