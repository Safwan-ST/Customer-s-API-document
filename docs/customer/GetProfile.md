### Customer Endpoints

### Get Customer Profile

**Endpoint**: `POST /api/Customer/Profile`

**Description**: Retrieves the customer's profile information, including a brief overview of statistics and wallet balance.

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): An object containing customer profile information:
  - `customer_id` (int): The customer's identifier.
  - `name` (string): The customer's name.
  - `eng_name` (string): The customer's name in English.
  - `phone` (string): The customer's phone number.
  - `email` (string): The customer's email address.
  - `username` (string): The customer's username.
  - `join_date` (string): The date the customer joined, in ISO 8601 format.
  - `wallet_balance` (int): The balance in the customer's wallet.
  - `cash_back_coupon` (object): Information about cashback coupons (if any).
  - `my_packages` (array): An array of packages owned by the customer, where each package contains:
    - `id` (int): The package identifier.
    - `package_expire_date` (string): The package expiration date, in ISO 8601 format.
    - `name` (string): The name of the package.
    - `eng_name` (string): The name of the package in English.
    - `service_id` (int): The service identifier associated with the package.
    - `package_service_id` (int): The package service identifier.
    - `service_name_in_the_package` (string): The service name in the package.
    - `service_eng_name_in_the_package` (string): The service name in the package in English.
    - `provider_id` (int): The provider identifier.
    - `provier_name` (string): The provider name.
    - `provier_eng_name` (string): The provider name in English.
    - `remaining_to_order` (int): The number of remaining orders for the package.
    - `history` (array): An array of history records for the package.
  - `statistics` (object): An object containing the customer's statistics:
    - `no_of_active_cars` (int): The number of active cars.
    - `no_of_paid_requests` (int): The number of paid requests.
    - `total_paid_invoices` (int): The total amount of paid invoices.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "customer_id": 10374,
    "name": "Ali JA",
    "eng_name": "Ali JA",
    "phone": "966555860161",
    "email": "sklafierenr@dn.ds",
    "username": "555860161",
    "join_date": "2024-06-16T23:47:25.387",
    "wallet_balance": 0,
    "cash_back_coupon": null,
    "my_packages": [
      {
        "id": 69,
        "package_expire_date": "2024-12-13T23:48:34.647",
        "name": "باقة غسيل اكسبرس",
        "eng_name": "Express wash package",
        "service_id": 10043,
        "package_service_id": 10022,
        "service_name_in_the_package": "غسيل اكسبريس",
        "service_eng_name_in_the_package": "Express Wash",
        "provider_id": 10317,
        "provier_name": "test222",
        "provier_eng_name": "test222",
        "remaining_to_order": 24,
        "history": []
      },
      {
        "id": 70,
        "package_expire_date": "2024-12-13T23:50:18.267",
        "name": "باقة غسيل اكسبرس",
        "eng_name": "Express wash package",
        "service_id": 10043,
        "package_service_id": 10022,
        "service_name_in_the_package": "غسيل اكسبريس",
        "service_eng_name_in_the_package": "Express Wash",
        "provider_id": 10317,
        "provier_name": "test222",
        "provier_eng_name": "test222",
        "remaining_to_order": 24,
        "history": []
      }
    ],
    "statistics": {
      "no_of_active_cars": 1,
      "no_of_paid_requests": 2,
      "total_paid_invoices": 900
    }
  }
}
```