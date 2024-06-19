## General Endpoints

### Get All Cars Models

**Endpoint**: `GET /api/General/Cars/Models`

**Description**: Retrieves a list of all car models, for getting models for a specific vendor `/api/General/Cars/Models/{id}`

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of car models, where each object contains:
  - `id` (int): The identifier for the car model.
  - `name` (string): The name of the car model in Arabic.
  - `eng_name` (string): The name of the car model in English.
  - `car_vendor_id` (int): The identifier of the car vendor to which the model belongs.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 93,
      "name": "كراون فكتوريا",
      "eng_name": "Crown Victoria",
      "car_vendor_id": 3
    },
    {
      "id": 94,
      "name": "ايدج",
      "eng_name": "Edge",
      "car_vendor_id": 3
    }
  ]
}
```