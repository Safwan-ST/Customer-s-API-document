### Get All Customer Cars

**Endpoint**: `POST /api/Customer/Cars`

**Description**: Retrieves all the cars that the customer has. for getting car by id use `POST /api/Customer/Car/{id}`

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of car objects, where each object contains:
  - `id` (int): The car ID.
  - `Car_Vendor_id` (int): The car vendor ID.
  - `Car_Model_id` (int): The car model ID.
  - `Car_Color_id` (int): The car color ID.
  - `Model_Year` (int): The model year of the car.
  - `Car_Lic_No` (string): The car license number.
  - `Board_No` (string): The board number of the car.
  - `is_active` (boolean): Indicates whether the car is active.
  - `Last_KMs_Usages` (int): The last recorded kilometers usage of the car.
  - `Cylinder_id` (int): The cylinder ID of the car.
  - `Car_Fule_Type_id` (int): The car fuel type ID.
  - `Vendor_name` (string): The name of the car vendor in Arabic.
  - `Vendor_egn_name` (string): The name of the car vendor in English.
  - `Models_name` (string): The name of the car model in Arabic.
  - `Models_eng_name` (string): The name of the car model in English.
  - `color_name` (string): The name of the car color in Arabic.
  - `color_eng_name` (string): The name of the car color in English.
  - `Fule_Type_name` (string): The name of the car fuel type in Arabic.
  - `Fule_Type_eng_name` (string): The name of the car fuel type in English.
  - `Vendors_binary_image` (string): The binary image of the car vendor.
  - `Car_Size_ID` (int): The car size ID.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": [
        {
            "id": 18871,
            "Car_Vendor_id": 1,
            "Car_Model_id": 11,
            "Car_Color_id": null,
            "Model_Year": null,
            "Car_Lic_No": "",
            "Board_No": "",
            "is_active": true,
            "Last_KMs_Usages": 46,
            "Cylinder_id": 46,
            "Car_Fule_Type_id": 1,
            "Vendor_name": "تويوتا",
            "Vendor_egn_name": "Toyota",
            "Models_name": "كامري",
            "Models_eng_name": "camry",
            "color_name": null,
            "color_eng_name": null,
            "Fule_Type_name": "بنزين",
            "Fule_Type_eng_name": "Petrol",
            "Vendors_binary_image": "",
            "Car_Size_ID": 1
        }
    ]
}
```
