### Ticket Categories

**Endpoint**: `GET /api/Tickets/TicktCategories`

**Description**: Retrieves the list of categories for the ticketing system.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**: None

**Response Parameters**:
- `status`: Indicates if the operation was successful (`true` or `false`).
- `message`: Describes the outcome of the operation.
- `error`: Provides details of any errors encountered during the operation.
- `Data`: An array of ticket categories, where each category includes:
  - `id`: The ID of the ticket category.
  - `name`: The name of the category in Arabic.
  - `eng_name`: The name of the category in English.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 2,
      "name": "لدي مشكلة في طلبي",
      "eng_name": "I have an issue on my order"
    },
    {
      "id": 4,
      "name": "اخرى",
      "eng_name": "Others"
    }
  ]
}
```
