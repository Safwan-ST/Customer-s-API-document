## General Endpoints

### 10. Get Cars Colors

**Endpoint**: `GET /api/General/Cars/Colors`

**Description**: Retrieves a list of car colors.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of car colors, where each object contains:
  - `id` (int): The identifier for the car color.
  - `name` (string): The name of the car color in Arabic.
  - `eng_name` (string): The name of the car color in English.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 1,
      "name": "ابيض ",
      "eng_name": "White"
    },
    {
      "id": 2,
      "name": "اسود",
      "eng_name": "Black"
    }
  ]
}
```