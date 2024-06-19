## General Endpoints

### Get Tire Specifications

#### Step 1: Get Available Widths

**Endpoint**: `GET /api/General/Services/Spesifications/List`

**Description**: Retrieves all available widths for Tire specifications related to a specific master service.

**Request Parameters**:
- `MasterServiceID` (int): The identifier of the master service (e.g., for Tires service).
- `PropertyName` (string): Specifies the property name for which values are being retrieved. Can be "Size", "Width", or "Height".

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

#### Step 2: Get Available Heights for a Width

**Endpoint**: `GET /api/General/Services/Spesifications/Distict/FilterHeights`

**Description**: Retrieves all available heights for a specific width in Tire specifications.

**Request Parameters**:
- `MasterServiceID` (int): The identifier of the master service (e.g., for Tires service).
- `Width` (int): The width value for which heights are being filtered.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of available heights, represented as integers.

**Response Example**
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    70,
    75
  ]
}
```

#### Step 3: Get Available Sizes for a Width and Height

**Endpoint**: `GET /api/General/Services/Spesifications/Distict/FilterSizes`

**Description**: Retrieves all available sizes for a specific width and height in Tire specifications.

**Request Parameters**:
- `MasterServiceID` (int): The identifier of the master service (e.g., for Tires service).
- `Width` (int): The width value for which sizes are being filtered.
- `Height` (int): The height value for which sizes are being filtered.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of available sizes, represented as integers.

**Response Example**
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    16,
    15
  ]
}
```

**Now you can go to the `/api/General/Services/Products/List` API**
