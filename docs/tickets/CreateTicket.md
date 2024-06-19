### Create Support Ticket

**Endpoint**: `POST /api/Tickets/Create`

**Description**: Creates a new support ticket. 

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Body Parameters**:
- `subject` (required): The subject of the ticket.
- `body` (required): The detailed description of the issue.
- `category_id` (required): The ID of the ticket category. Comes from this [API](TicketsCategories.md)
- `related_request_id` (optional): The ID of the related request, if applicable.
- `files` (optional): An array of files to be attached to the ticket. Each file object includes:
  - `file_name_with_extension`: The name of the file with its extension ex 'image.jpg'.
  - `content`: The binary content of the file.

**Response Parameters**:
- `status`: Indicates if the operation was successful (`true` or `false`).
- `message`: Describes the outcome of the operation.
- `error`: Provides details of any errors encountered during the operation.
- `Data`: Contains additional data related to the operation.
  - `id`: The ID of the created support ticket.

#### Example

**Request**:
```json
{
    "subject": "لم يتم الحضور في الموعد",
    "body": "لم يتم الحضور في الموعد وصف",
    "category_id": 2,
    "related_request_id": 16970,
    "files": [
        {
            "file_name_with_extension": "image0.jpg",
            "content": "Binary Image"
        }
    ]
}
```

**Response**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "id": 221
  }
}
```