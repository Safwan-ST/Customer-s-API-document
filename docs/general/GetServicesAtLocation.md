## General Endpoints

### Get Location Advance

**Endpoint**: `GET /api/General/Location/GetLocationAdvance`

**Description**: This endpoint returns the services available at a given location based on latitude and longitude.

**Request URL Example**:
https://satc.live/api/General/Location/GetLocationAdvance?lat=24.701139&lng=46.641366

**Request Parameters**:
- `lat` (double): The latitude of the location.
  - **Example**: `24.701139`
- `lng` (double): The longitude of the location.
  - **Example**: `46.641366`

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): An object containing the following fields when services are available:
  - `id` (integer): The location ID.
  - `name` (string): The name of the location in Arabic.
  - `eng_name` (string): The name of the location in English.
  - `zone_id` (integer): The zone ID.
  - `zone_name` (string): The name of the zone in Arabic.
  - `zone_eng_name` (string): The name of the zone in English.
  - `city_id` (integer): The city ID.
  - `city_name` (string): The name of the city in Arabic.
  - `city_eng_name` (string): The name of the city in English.
  - `suggested_lat` (double): The suggested latitude for the location.
  - `suggested_lng` (double): The suggested longitude for the location.
  - `services` (array): An array of service objects, each containing the following fields:
    - `id` (integer): The service ID.
    - `name` (string): The name of the service in Arabic.
    - `eng_name` (string): The name of the service in English.
    - `service_master_group_id` (integer): The service master group ID.
    - `force_advance_payment` (boolean): Indicates whether advance payment is required.
    - `allow_appointment` (boolean): Indicates whether appointment booking is allowed.
    - `service_master_group_name` (string): The service master group name in Arabic.
    - `service_master_group_eng_name` (string): The service master group name in English.
    - `is_simple_service` (boolean): Indicates whether it is a simple service.
    - `is_for_vehicle_repair` (boolean): Indicates whether the service is for vehicle repair.
    - `allow_mutli_providers_choices` (boolean): Indicates whether multiple provider choices are allowed.
    - `allow_mutli_check_on_products` (boolean): Indicates whether multiple checks on products are allowed.
    - `is_for_oil` (boolean): Indicates whether the service is for oil.
    - `is_for_tires` (boolean): Indicates whether the service is for tires.
    - `is_for_battaries` (boolean): Indicates whether the service is for batteries.
    - `is_required_attachments_on_new_request` (boolean): Indicates whether attachments are required on new requests.
    - `min_attachment_files` (integer|null): The minimum number of attachment files required.
    - `max_attachment_files` (integer|null): The maximum number of attachment files allowed.
    - `Order_No` (integer): The order number of the service.
    - `link` (string): The link to the service image.
    - `force_payment_after_creating_order` (boolean): Indicates whether payment is forced after creating the order.
    - `is_package_service` (boolean): Indicates whether it is a package service.
    - `is_shipping_service` (boolean): Indicates whether it is a shipping service.
  - `ads` (array): An array of advertisement objects, each containing the following fields:
    - `id` (integer): The advertisement ID.
    - `name` (string): The name of the advertisement.
    - `description` (string|null): The description of the advertisement.
    - `order` (integer): The order number of the advertisement.
    - `link` (string): The link to the advertisement image.
    - `image` (string|null): The image URL of the advertisement.

**Response Example (No Services Available):**
```json
{
  "status": false,
  "message": "لم يتم العثور على أية خدمات في هذه الإحداثيات",
  "error": "لم يتم العثور على أية خدمات في هذه الإحداثيات",
  "Data": null
}
```

**Response Example (Services Available):**
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "id": 40,
    "name": "الرائد",
    "eng_name": "Al Raed",
    "zone_id": 13,
    "zone_name": "R8",
    "zone_eng_name": "R8",
    "city_id": 1,
    "city_name": "الرياض",
    "city_eng_name": "Riyadh",
    "suggested_lat": 24.707954448228314,
    "suggested_lng": 46.64021392352765,
    "services": [
      {
        "id": 2,
        "name": "تبديل البطاريات ",
        "eng_name": "Battery Services",
        "service_master_group_id": 1,
        "force_advance_payment": false,
        "allow_appointment": true,
        "service_master_group_name": "الخدمات المتنقله",
        "service_master_group_eng_name": "Mobile services",
        "is_simple_service": false,
        "is_for_vehicle_repair": false,
        "allow_mutli_providers_choices": true,
        "allow_mutli_check_on_products": false,
        "is_for_oil": false,
        "is_for_tires": false,
        "is_for_battaries": true,
        "is_required_attachments_on_new_request": false,
        "min_attachment_files": null,
        "max_attachment_files": null,
        "Order_No": 6,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2Fa325c184-3f07-43eb-93c9-0d55f1e2417afile.png?alt=media&token=58d0bbe4-df6c-4578-9665-85e50d92be23",
        "force_payment_after_creating_order": false,
        "is_package_service": false,
        "is_shipping_service": false,
      },
      {
        "id": 3,
        "name": "تبديل الكفرات ",
        "eng_name": "Tires Services",
        "service_master_group_id": 1,
        "force_advance_payment": false,
        "allow_appointment": true,
        "service_master_group_name": "الخدمات المتنقله",
        "service_master_group_eng_name": "Mobile services",
        "is_simple_service": false,
        "is_for_vehicle_repair": false,
        "allow_mutli_providers_choices": true,
        "allow_mutli_check_on_products": false,
        "is_for_oil": false,
        "is_for_tires": true,
        "is_for_battaries": false,
        "is_required_attachments_on_new_request": false,
        "min_attachment_files": null,
        "max_attachment_files": null,
        "Order_No": 1,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2F756d48aa-4788-4522-890d-3064f1a0cde6file.png?alt=media&token=551a9400-9252-4ed1-87ba-a836b1b582fc",
        "force_payment_after_creating_order": false,
        "is_package_service": false,
        "is_shipping_service": false,
      },
      {
        "id": 4,
        "name": "غسيل السيارات",
        "eng_name": "Car Wash Service",
        "service_master_group_id": 1,
        "force_advance_payment": true,
        "allow_appointment": true,
        "service_master_group_name": "الخدمات المتنقله",
        "service_master_group_eng_name": "Mobile services",
        "is_simple_service": true,
        "is_for_vehicle_repair": false,
        "allow_mutli_providers_choices": true,
        "allow_mutli_check_on_products": false,
        "is_for_oil": false,
        "is_for_tires": false,
        "is_for_battaries": false,
        "is_required_attachments_on_new_request": false,
        "min_attachment_files": null,
        "max_attachment_files": null,
        "Order_No": 4,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2F29e6c4af-5393-4994-8d02-b89b5cd3120efile.png?alt=media&token=75a8bb73-128d-44fa-b71c-bda7c653d965",
        "force_payment_after_creating_order": false,
        "is_package_service": false,
        "is_shipping_service": false,
        "payment_gateways": []
      },
      {
        "id": 5,
        "name": "تغيير الزيت",
        "eng_name": "Change Oil",
        "service_master_group_id": 1,
        "force_advance_payment": false,
        "allow_appointment": true,
        "service_master_group_name": "الخدمات المتنقله",
        "service_master_group_eng_name": "Mobile services",
        "is_simple_service": false,
        "is_for_vehicle_repair": false,
        "allow_mutli_providers_choices": true,
        "allow_mutli_check_on_products": false,
        "is_for_oil": true,
        "is_for_tires": false,
        "is_for_battaries": false,
        "is_required_attachments_on_new_request": false,
        "min_attachment_files": null,
        "max_attachment_files": null,
        "Order_No": 5,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2Fbe2e673e-34aa-4013-abcf-3a20885456f0file.png?alt=media&token=6fbb1c17-7c97-4e19-9c1e-09ea80bdbca3",
        "force_payment_after_creating_order": false,
        "is_package_service": false,
        "is_shipping_service": false,
      }
    ],
    "ads": [
      {
        "id": 29,
        "name": "Test for cities",
        "description": null,
        "order": 2,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2F57e06972-e67d-4165-a71c-b52f670ce1f4file.png?alt=media&token=ae654e13-99ff-4b79-bd34-21385b90c022",
        "image": null
      },
      {
        "id": 20,
        "name": "صلح سيارتك مع سيارتك",
        "description": "Store Only",
        "order": 4,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2F94d73942-cd6a-40b6-806f-a0c36db7730cfile.png?alt=media&token=bbeb69f6-19b7-4371-b82e-f473092228be",
        "image": null
      },
      {
        "id": 25,
        "name": "قسطها مع تابي",
        "description": "Sayaratech Store",
        "order": 9,
        "link": "https://firebasestorage.googleapis.com/v0/b/sayaratech-97a41.appspot.com/o/data%2Frandom%2Fd97e2860-3206-4652-94e7-2240a605b708file.png?alt=media&token=f20af876-3b6b-4a02-aa00-b6b8331cfc9b",
        "image": null
      }
    ]
  }
}

```