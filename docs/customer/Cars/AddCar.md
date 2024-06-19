### Add a Car

**Endpoint**: `POST /api/Customer/AddCar`

**Description**: Adds a new car to the customer's profile.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Body Parameters**:
- `Car_Vendor_id` (int, required): The car vendor ID.
- `Car_Model_id` (int, required): The car model ID.
- `Car_Color_id` (int): The car color ID.
- `Model_Year` (int): The model year of the car.
- `Board_No` (string): The board number of the car.
- `Car_Lic_No` (string): The car license number.
- `Last_KMs_Usages` (int): The last recorded kilometers usage of the car.
- `Car_Models_Engine_id` (int, required): The cylinder ID of the car.
- `Car_Fule_Type_id` (int, required): The car fuel type ID.

**Request Body Example**:
```json
{
    "Car_Vendor_id": 1,
    "Car_Model_id": 12,
    "Car_Color_id": 8,
    "Model_Year": 2023,
    "Board_No": "FJJFJRU223",
    "Car_Lic_No": "123 A A A",
    "Last_KMs_Usages": 47,
    "Car_Models_Engine_id": 47,
    "Car_Fule_Type_id": 2
}
```

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (int): The ID of the newly added car.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": 18873
}
```