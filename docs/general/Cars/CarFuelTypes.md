## General Endpoints

### Get Car Fuel Types

**Endpoint**: `GET /api/General/Cars/FuelTypes`

**Description**: Retrieves the available fuel types for cars.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of car fuel types, where each object contains:
  - `id` (int): The identifier for the car fuel type.
  - `name` (string): The name of the car fuel in Arabic.
  - `eng_name` (string): The name of the car fuel in English.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 1,
      "name": "بنزين",
      "eng_name": "Petrol"
    },
    {
      "id": 2,
      "name": "ديزل",
      "eng_name": "Diesel"
    },
    {
      "id": 3,
      "name": "كهربائيه",
      "eng_name": "Eelectric"
    },
    {
      "id": 4,
      "name": "هجين",
      "eng_name": "Hybrid"
    }
  ]
}
```