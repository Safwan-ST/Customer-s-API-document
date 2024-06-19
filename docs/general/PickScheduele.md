## General Endpoints

### Pick Schedule Service

**Endpoint**: `POST /api/General/Services/Request/PickScheduleService`

**Description**: Initiates a request to pick a schedule for a service.

**Request Parameters**:
- `MasterServiceID` (integer): The ID of the master service.
- `ProviderID` (integer): The ID of the service provider.
- `AreaID` (integer): The ID of the area where the service will be provided.
- `CarVendorID` (integer): The ID of the car vendor.

**Example Request**: `https://satc.live/api/General/Services/Request/PickScheduleService?MasterServiceID=10022&ProviderID=10031&AreaID=41&CarVendorID=3`

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array containing schedule details, where each object contains:
  - `date` (string): The date of the scheduled service.
  - `dayname` (string): The day name corresponding to the date.
  - `hours` (array): An array of available hours, where each object contains:
    - `provider_id` (integer): The ID of the service provider.
    - `branch_id` (integer): The ID of the branch provider to handle the service.
    - `user_id` (integer): The ID of the employee user to handle the service.
    - `hour` (integer): The available hour.
    - `minute` (string): The minute of the available hour (e.g., "00", "15", "30", "45").

**Response Example**:

```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "date": "6/17/2024",
      "dayname": "الأثنين",
      "hours": [
        {
          "provider_id": 10317,
          "branch_id": 220,
          "user_id": 21275,
          "hour": 3,
          "minute": "00"
        }
      ]
    }
  ]
}
```