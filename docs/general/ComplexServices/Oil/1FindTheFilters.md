## General Endpoints

### Get Filters for Oil Service

#### Endpoint: `GET /api/General/Services/Products/Filters/{id}`

Retrieves available filters for the oil service identified by `{id}`. You will use the filter id from the response into the `POST /api/General/Services/Request/Providers` in the items IDs list inside the body

**Request Parameters**:
- `id` (int): The identifier of the oil service which is 5.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of filter options for the oil service, where each object contains:
  - `id` (int): The identifier of the filter.
  - `name` (string): The name of the filter in Arabic.
  - `eng_name` (string): The name of the filter in English.
  - `service_brand_id` (int): The identifier of the brand associated with the filter.
  - `brand_name` (string): The name of the brand in Arabic.
  - `brand_eng_name` (string): The name of the brand in English.
  - `service_name` (string): The name of the service in Arabic.
  - `service_eng_name` (string, nullable): The name of the service in English.
  - `binary_image` (string): Base64 encoded binary image of the filter.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": [
        {
            "id": 10056,
            "name": "فلتر هواء المقصورة ",
            "eng_name": "Cabin Air Fillter",
            "service_brand_id": 31,
            "brand_name": "الفلاتر ",
            "brand_eng_name": "Filters",
            "service_name": "تفاصيل الخدمة ",
            "service_eng_name": null,
            "binary_image": ""
        },
        {
            "id": 10057,
            "name": "فلتر الهواء",
            "eng_name": "Air Filter",
            "service_brand_id": 31,
            "brand_name": "الفلاتر ",
            "brand_eng_name": "Filters",
            "service_name": "تفاصيل الخدمة ",
            "service_eng_name": null,
            "binary_image": ""
        }
    ]
}
```

**Now you can go to the `GET /api/General/Services/Products/Brands/{id}` API**
