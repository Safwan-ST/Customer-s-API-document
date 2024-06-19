
### Step2: Get Items by Brand

#### Endpoint: `GET /api/General/Services/Products/ItemsByBrand/{id}`

Retrieves items for the specified brand.

**Request Parameters**:
- `id` (int, required): The identifier of the brand.
- `area_id` (int): Area ID to filter items supporting this area.
- `car_vendor_id` (int): Car Vendor ID to filter items supporting this type of car.
- `car_cylinder_id` (int): Car Cylinder ID to filter items supporting this cylinder type.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of items, where each object contains:
  - `id` (int): The identifier of the item.
  - `name` (string): The name of the item in Arabic.
  - `eng_name` (string): The name of the item in English.
  - `service_brand_id` (int): The identifier of the service brand.
  - `brand_name` (string): The name of the brand in Arabic.
  - `brand_eng_name` (string): The name of the brand in English.
  - `service_name` (string): The name of the service in Arabic.
  - `service_eng_name` (string): The name of the service in English.
  - `price` (float): The price of the item.
  - `validity_by_kms` (int, nullable): The validity of the item by kilometers.
  - `binary_image` (string): Base64 encoded binary image of the item.

**Response Example**
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": [
        {
            "id": 62,
            "name": "غسيل بلس خارجي ",
            "eng_name": "WashPlus Enternal ",
            "service_brand_id": 28,
            "brand_name": "بلس",
            "brand_eng_name": "Plus",
            "service_name": "غسيل ظغط ماء عالي",
            "service_eng_name": "High water pressure washing",
            "price": 0,
            "validity_by_kms": null,
            "binary_image": ""
        },
        {
            "id": 64,
            "name": "غسيل بلس خارجي و داخلي ",
            "eng_name": "WashPlus External and Enternalh",
            "service_brand_id": 28,
            "brand_name": "بلس",
            "brand_eng_name": "Plus",
            "service_name": "غسيل ظغط ماء عالي",
            "service_eng_name": "High water pressure washing",
            "price": 0,
            "validity_by_kms": null,
            "binary_image": ""
        }
    ]
}
```