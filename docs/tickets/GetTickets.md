### List Support Tickets

**Endpoint**: `GET /api/Tickets/List`

**Description**: Retrieves a list of support tickets.

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status`: Indicates if the operation was successful (`true` or `false`).
- `message`: Describes the outcome of the operation.
- `error`: Provides details of any errors encountered during the operation.
- `Data`: Contains the list of support tickets and pagination information.
  - `List`: An array of support tickets. Each ticket object includes:
    - `id`: The ID of the ticket.
    - `subject`: The subject of the ticket.
    - `status_id`: The ID of the ticket status.
    - `status_name`: The name of the ticket status in Arabic.
    - `status_eng_name`: The name of the ticket status in English.
    - `status_color`: The color associated with the ticket status.
    - `created_by`: The ID of the user who created the ticket.
    - `created_by_name`: The name of the user who created the ticket.
    - `created_date`: The date and time when the ticket was created.
    - `body`: The detailed description of the issue.
    - `is_closed`: Indicates if the ticket is closed (`true` or `false`).
    - `closed_date`: The date and time when the ticket was closed, if applicable.
    - `category_id`: The ID of the ticket category.
    - `category_name`: The name of the ticket category in Arabic.
    - `category_eng_name`: The name of the ticket category in English.
    - `related_request_id`: The ID of the related request, if applicable.
  - `PageNumber`: The current page number.
  - `PageSize`: The number of tickets per page.
  - `PageCount`: The total number of pages.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "List": [
      {
        "id": 221,
        "subject": "لم يتم الحضور في الموعد",
        "status_id": 0,
        "status_name": "جديد",
        "status_eng_name": "New",
        "status_color": "#fc8403",
        "created_by": 21369,
        "created_by_name": "Jamal Khalid",
        "created_date": "2024-06-20T01:10:09.687",
        "body": "لم يتم الحضور في الموعد وصف",
        "is_closed": false,
        "closed_date": null,
        "category_id": 2,
        "category_name": "لدي مشكلة في طلبي",
        "category_eng_name": "I have an issue on my order",
        "related_request_id": 16970
      }
    ],
    "PageNumber": 1,
    "PageSize": 12,
    "PageCount": 1
  }
}
```