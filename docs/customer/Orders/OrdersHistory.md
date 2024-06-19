### Get List of Paid Orders

**Endpoint**: `GET /api/Customer/Orders/PaidList`

**Description**: Retrieves a list of paid booking orders.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters** (optional):
- `PageIndex` (integer): The page number to retrieve.
- `PageSize` (integer): The number of items per page.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): Contains the following fields:
  - `List` (array): A list of paid orders, each containing:
    - `request_id` (integer): The request ID.
    - `id` (integer): The order ID.
    - `InvoiceNumber` (string): The invoice number.
    - `Paid_Date` (string): The date and time when the order was paid.
    - `Grand_Total` (number): The total amount of the order.
    - `Paid_Amount` (number): The amount paid for the order.
    - `Paid_Amount_To_Wallet` (number): The amount paid to the wallet.
    - `master_service_id` (integer): The master service ID.
    - `service_name` (string): The name of the service in Arabic.
    - `service_eng_name` (string): The name of the service in English.
    - `Payment_Options_id` (integer): The ID of the payment option.
    - `Payment_Options_name` (string): The name of the payment option in Arabic.
    - `Payment_Options_eng_name` (string): The name of the payment option in English.
    - `is_simple_service` (boolean): Indicates if the service is a simple service.
    - `is_for_vehicle_repair` (boolean): Indicates if the service is for vehicle repair.
    - `is_for_oil` (boolean): Indicates if the service is for oil.
    - `is_for_tires` (boolean): Indicates if the service is for tires.
    - `is_for_battaries` (boolean): Indicates if the service is for batteries.
    - `is_package_service` (boolean): Indicates if the service is a package service.
    - `is_shipping_service` (boolean): Indicates if the service is a shipping service.
    - `is_for_pickup` (boolean or null): Indicates if the service is for pickup.
    - `service_img` (string or null): The image of the service.
  - `PageNumber` (integer): The current page number.
  - `PageSize` (integer): The number of items per page.
  - `PageCount` (integer): The total number of pages.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "List": [
      {
        "request_id": 16964,
        "id": 17082,
        "InvoiceNumber": "3722",
        "Paid_Date": "2024-06-19T02:44:53.807",
        "Grand_Total": 140,
        "Paid_Amount": 140,
        "Paid_Amount_To_Wallet": 0,
        "master_service_id": 10022,
        "service_name": "غسيل اكسبريس",
        "service_eng_name": "Express Wash",
        "Payment_Options_id": 3,
        "Payment_Options_name": "كاش ومحفظة",
        "Payment_Options_eng_name": "Cash And Wallet",
        "is_simple_service": true,
        "is_for_vehicle_repair": false,
        "is_for_oil": false,
        "is_for_tires": false,
        "is_for_battaries": false,
        "is_package_service": false,
        "is_shipping_service": false,
        "is_for_pickup": null,
        "service_img": null
      }
    ],
    "PageNumber": 1,
    "PageSize": 12,
    "PageCount": 1
  }
}
```