## General Endpoints

### Get Car Model Cylinders

**Endpoint**: `GET /api/General/Cars/Models/Cylinder/{id}`

**Description**: Retrieves the cylinders available for a specific car model identified by `{id}`.

**Request Parameters**:
- `{id}` (int): The identifier for the car model.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of cylinders available for the car model, where each object contains:
  - `id` (int): The identifier for the cylinder.
  - `name` (int): The number of cylinders.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 145,
      "name": 6
    },
    {
      "id": 146,
      "name": 8
    }
  ]
}
```