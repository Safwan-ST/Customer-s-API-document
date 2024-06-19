### 13. Add New Address

**Endpoint**: `POST /api/Customer/NewAddress`

**Description**: Adds a new address for the customer.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Body**:
- `address_type_id`: ID of the address type (integer).
- `lat`: Latitude of the address (string).
- `lng`: Longitude of the address (string).
- `city_id`: ID of the city (integer).
- `zone_id`: ID of the zone (integer).
- `area_id`: ID of the area (integer).
- `loc_desc`: Description of the location (string, optional).

**Request Body Example**:
```json
{
    "address_type_id": 1,
    "lat": "24.689679152149406",
    "lng": "46.62728983908892",
    "city_id": 1,
    "zone_id": 13,
    "area_id": 41,
    "loc_desc": null
}
```

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (int): The ID of the newly added address.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": 9658
}
```
