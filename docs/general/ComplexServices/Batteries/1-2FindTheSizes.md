## General Endpoints

### Get Battery Specifications

#### Step 1: Get Available Widths

**Endpoint**: `GET /api/General/Services/Spesifications/List`

**Description**: Retrieves all available widths for Battery specifications related to a specific master service.

**Request Parameters**:
- `MasterServiceID` (int): The identifier of the master service (e.g., for Batteries service).
- `PropertyName` (string): Specifies the property name for which values are being retrieved. Can be "Size".

**Request Example**:
`https://satc.live/api/General/Services/Spesifications/List?MasterServiceID=2&PropertyName=Size`

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of available widths (or sizes or heights), represented as strings.

**Response Example**
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    "165",
    "305",
    "315"
  ]
}
```

**Now you can go to the `/api/General/Services/Products/List` API**
