## General Endpoints

### Verify Version

**Endpoint**: `GET /api/General/App/Customers/VerifyVersion`

**Description**: This endpoint checks the current version of the application to determine if a forced update is required.

**Request URL Example**:
https://satc.live/api/General/App/Customers/VerifyVersion?version=2.1.3

**Request Parameters**:
- `version` (string): The current version of the application.
  - **Example**: `2.1.3`

**Response Examples**:
**When no force update triggered**
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "force_update": false,
    "msg": "",
    "msg_eng": ""
  }
}
```
**When force update triggered**
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "force_update": true,
    "msg": "يوجد نسخة جديدة من التطبيق",
    "msg_eng": "There is a new version of the application"
  }
}
```

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): An object containing the following fields:
  - `force_update` (boolean): Indicates whether a forced update is required.
  - `msg` (string): A message in Arabic regarding the update status.
  - `msg_eng` (string): A message in English regarding the update status.
