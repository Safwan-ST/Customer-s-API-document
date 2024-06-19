## General Endpoints

### Validate Coupon

**Endpoint**: `POST /api/General/Services/Sales/ValidateCoupon`

**Description**: Validates a coupon for a specific service and provider, optionally applying to a customer and products.

**Request Parameters**:
- `CouponName` (string): The name of the coupon to be validated.
- `MasterServiceID` (int): The ID of the master service.
- `ProviderID` (int): The ID of the provider.
- `products` (array): An array of item IDs representing the products.
- `apply_to_customer_id` (int): The ID of the customer to apply the coupon to.

**Headers**:
- `authorization`: Bearer token for authentication (e.g., `'authorization': 'Bearer {token}'`).

**Example Request**:
[Validate Coupon Request Example](https://satc.live/api/General/Services/Sales/ValidateCoupon?CouponName=testab&MasterServiceID=10022&ProviderID=10031&products=[]&apply_to_customer_id=10374)

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): Contains the validation details:
  - `coupon_id` (int): The identifier for the coupon.
  - `percentage_discount` (float): The percentage discount offered by the coupon.
  - `fixed_discount` (float): The fixed discount amount offered by the coupon.
  - `cash_back_expire_in_days` (int, nullable): The number of days until the cash back offer expires.
  - `cash_back_amount` (float, nullable): The cash back amount offered.
  - `cash_back_percentage` (float, nullable): The cash back percentage offered.

**Response Example**:
```json
{
    "status": true,
    "message": "الخصم 30.00 %",
    "error": "",
    "Data": {
        "coupon_id": 78,
        "percentage_discount": 30.0000,
        "fixed_discount": 0.0000,
        "cash_back_expire_in_days": null,
        "cash_back_amount": null,
        "cash_back_percentage": null
    }
}
```