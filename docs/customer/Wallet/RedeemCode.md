## Add Amount to Wallet

**Endpoint**: `POST /api/Customer/Profile/Redeem/AddToWallet`

**Description**: Add an amount to the customer's wallet from a coupon that is scanned or entered manually.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `code` (required, string): The coupon code to redeem.

**Response Parameters**:
- `status` (boolean): Indicates if the operation was successful (`true` or `false`).
- `message` (string): Describes the outcome of the operation.
- `error` (string): Provides details of any errors encountered during the operation.
- `Data` (object): Contains additional data related to the operation.
  - `added_amount` (number): The amount added to the wallet.
  - `expired_date` (string, DateTime): The expiration date of the added amount.
  - `new_wallet_balance` (number): The new balance of the wallet after the amount is added.
  - `desc` (string): Any description or details about the operation.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": {
        "added_amount": 300.5,
        "expired_date": "2024-12-31T23:59:59",
        "new_wallet_balance": 405.3,
        "desc": "Coupon redeemed successfully"
    }
}
```