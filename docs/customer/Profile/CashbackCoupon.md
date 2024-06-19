### Request and Activate Cash Back Coupon

**Endpoint**: `POST /api/Customer/RequestCashBackCoupon`

**Description**: Requests and activates a cash back coupon for the customer.

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): Contains the details of the cash back coupon.
  - `cash_back_coupon` (object): The cash back coupon details.
    - `code` (string): The coupon code.
    - `is_active` (boolean): Indicates whether the coupon is active.
    - `cash_back_money` (number): The amount of cash back money.
    - `desc` (string): Description of the cash back offer.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": {
        "cash_back_coupon": {
            "code": "BO310375",
            "is_active": true,
            "cash_back_money": 40,
            "desc": "شارك رمزك مع أصدقائك واحصل على استرداد نقدي 40.00 في محفظتك"
        }
    }
}
```