## General Endpoints

### Get Car Fuel Types

**Endpoint**: `GET /api/General/Cars/FuelTypes`

**Description**: Retrieves the available fuel types for cars.

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