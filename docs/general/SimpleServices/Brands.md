## General Endpoints

### Step1: Get Brands for Master Service

#### Endpoint: `GET /api/General/Services/Products/Brands/{id}`

Retrieves available brands for products of the specified master service.

**Request Parameters**:
- `id` (int, required): The identifier of the master service.
- `area_id` (int): Area ID to filter brands supporting this area.
- `car_vendor_id` (int): Car Vendor ID to filter brands supporting this type of car.
- `car_model_id` (int): Car Model ID to filter brands supporting this model.
- `car_cylinder_id` (int): Car Cylinder ID to filter brands supporting this cylinder type.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of brands, where each object contains:
  - `id` (int): The identifier of the brand.
  - `name` (string): The name of the brand in Arabic.
  - `eng_name` (string): The name of the brand in English.
  - `desc` (string, nullable): The description of the brand in Arabic.
  - `eng_desc` (string, nullable): The description of the brand in English.
  - `service_name` (string): The name of the service in Arabic.
  - `binary_image` (string): Base64 encoded binary image of the brand.
  - `Car_Size_ID` (int, nullable): The identifier of the car size.
  - `IsVirtualBrand` (boolean): Indicates if it is a virtual brand.
  - `items` (array): An array of items under this brand, where each item contains:
    - `id` (int): The identifier of the item.
    - `name` (string): The name of the item in Arabic.
    - `eng_name` (string): The name of the item in English.
    - `desc` (string, nullable): The description of the item in Arabic.
    - `eng_desc` (string, nullable): The description of the item in English.
    - `validity_by_kms` (int, nullable): The validity of the item by kilometers.
    - `binary_image` (string, nullable): Base64 encoded binary image of the item.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": [
        {
            "id": 28,
            "name": "بلس",
            "eng_name": "Plus",
            "desc": null,
            "eng_desc": null,
            "service_name": "غسيل ظغط ماء عالي",
            "binary_image": "",
            "Car_Size_ID": 2,
            "IsVirtualBrand": false,
            "items": [
                {
                    "id": 62,
                    "name": "غسيل بلس خارجي ",
                    "eng_name": "WashPlus Enternal ",
                    "desc": null,
                    "eng_desc": null,
                    "validity_by_kms": null,
                    "binary_image": null
                },
                {
                    "id": 64,
                    "name": "غسيل بلس خارجي و داخلي ",
                    "eng_name": "WashPlus External and Enternalh",
                    "desc": "غسيل بلس خارجي بشامبو سيارات وتنظيف داخلي بمكينة شفط وبفوط مايكروفايبر الأولى",
                    "eng_desc": "غسيل بلس خارجي بشامبو سيارات وتنظيف داخلي بمكينة شفط وبفوط مايكروفايبر الأولى",
                    "validity_by_kms": null,
                    "binary_image": null
                }
            ]
        },
        {
            "id": 80,
            "name": "اكسبريس",
            "eng_name": "Express",
            "desc": null,
            "eng_desc": null,
            "service_name": "غسيل  ",
            "binary_image": "",
            "Car_Size_ID": 2,
            "IsVirtualBrand": false,
            "items": [
                {
                    "id": 10140,
                    "name": "غسيل اكسبريس داخلي وخارجي ",
                    "eng_name": "WashExpress external and enternal ",
                    "desc": null,
                    "eng_desc": "express Indoor and outdoor washing",
                    "validity_by_kms": null,
                    "binary_image": null
                }
            ]
        },
        {
            "id": 88,
            "name": "بخار ",
            "eng_name": "Steam",
            "desc": null,
            "eng_desc": null,
            "service_name": "بالبخار ",
            "binary_image": "",
            "Car_Size_ID": 2,
            "IsVirtualBrand": false,
            "items": [
                {
                    "id": 10624,
                    "name": "غسيل بخار خارجي و داخلي ",
                    "eng_name": "SteamWash external and enternal ",
                    "desc": null,
                    "eng_desc": null,
                    "validity_by_kms": null,
                    "binary_image": ""
                }
            ]
        }
    ]
}
```
