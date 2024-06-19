### Get Customer Addresses

**Endpoint**: `POST /api/Customer/Addresses`

**Description**: Retrieves all addresses associated with the customer's profile. for getting address by id use `POST /api/Customer/Address/{id}`

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of address objects, where each object contains:
  - `id` (int): The identifier for the address.
  - `city_id` (int): The city ID.
  - `zone_id` (int): The zone ID.
  - `area_id` (int): The area ID.
  - `address_type_id` (int): The address type ID.
  - `lat` (string): The latitude of the address.
  - `lng` (string): The longitude of the address.
  - `loc_desc` (string): A description of the location.
  - `City_name` (string): The name of the city in Arabic.
  - `City_eng_name` (string): The name of the city in English.
  - `Zone_name` (string): The name of the zone in Arabic.
  - `Zone_eng_name` (string): The name of the zone in English.
  - `Area_name` (string): The name of the area in Arabic.
  - `Area_eng_name` (string): The name of the area in English.
  - `AddressType_name` (string): The name of the address type in Arabic.
  - `AddressType_eng_name` (string): The name of the address type in English.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": [
        {
            "id": 9656,
            "city_id": 1,
            "zone_id": 13,
            "area_id": 41,
            "address_type_id": 10,
            "lat": "24.689679",
            "lng": "46.62729",
            "loc_desc": "",
            "City_name": "الرياض",
            "City_eng_name": "Riyadh",
            "Zone_name": "R8",
            "Zone_eng_name": "R8",
            "Area_name": "السفارات",
            "Area_eng_name": "Al Safarat",
            "AddressType_name": "آخر",
            "AddressType_eng_name": "Other"
        }
    ]
}
```
