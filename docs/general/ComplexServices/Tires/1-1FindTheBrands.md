## General Endpoints

### Get Products Brands by Master Service ID

**Endpoint**: `GET /api/General/Services/Products/Brands/{id}`

**Description**: Retrieves brands of products associated with a specific master service ID.

**Request Parameters**:
- `id` (int): (required) The identifier of the master service for which brands are being retrieved.
- `area_id` (int): Area ID To show only brands that support this area
- `car_vendor_id` (int): Car Vendor To show only brands that support this Type of car 
- `car_model_id` (int): Car Model To show only brands that support this Type of car
- `car_cylinder_id` (int): Car Cylinder To show only brands that support this Type of car

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of brand objects, where each object contains:
  - `id` (int): The identifier of the brand.
  - `name` (string): The name of the brand in Arabic.
  - `eng_name` (string): The name of the brand in English.
  - `desc` (string, optional): Description of the brand in Arabic (if available).
  - `eng_desc` (string, optional): Description of the brand in English (if available).
  - `service_name` (string): The name of the master service associated with the brand.
  - `binary_image` (string, optional): Binary image data of the brand's logo or image.
  - `Car_Size_ID` (int, optional): Identifier of the car size associated with the brand.
  - `IsVirtualBrand` (boolean): Indicates if the brand is virtual.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 17,
      "name": "هانكوك",
      "eng_name": "Hankook",
      "desc": null,
      "eng_desc": null,
      "service_name": "خدمة البطاريات ",
      "binary_image": "iVdkfkdfdf...",
      "Car_Size_ID": null,
      "IsVirtualBrand": false
    }
  ]
}
```

**Now you can go to the `/api/General/Services/Products/List` API**
