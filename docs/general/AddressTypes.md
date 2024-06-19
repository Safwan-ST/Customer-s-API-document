## General Endpoints

### 5. Get Address Types

**Endpoint**: `GET /api/General/AddressTypes`

**Description**: This endpoint retrieves a list of address types.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of address types, where each object contains:
  - `id` (int): The identifier for the address type.
  - `name` (string): The name of the address type in Arabic.
  - `eng_name` (string): The name of the address type in English.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 1,
      "name": "المنزل",
      "eng_name": "Home"
    },
    {
      "id": 2,
      "name": "العمل",
      "eng_name": "Work"
    },
    {
      "id": 3,
      "name": "منزل صديق",
      "eng_name": "Friend Home"
    },
    {
      "id": 10,
      "name": "آخر",
      "eng_name": "Other"
    }
  ]
}
```