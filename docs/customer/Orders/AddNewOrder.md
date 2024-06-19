### 21. Add New Order Request

**Endpoint**: `POST /api/Customer/Orders/AddNewRequest`

**Description**: Creates a new order request for a specified service.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Body**:
- `MasterServiceID` (integer, required): The ID of the master service.
- `ProviderID` (integer, required): The ID of the service provider.
- `CarID` (integer, required): The ID of the car associated with the service.
- `Lng` (number, required): The longitude of the service location is the same as when requesting this API `GET /api/General/Location/GetLocationAdvance`, don't use current location always.
- `Lat` (number, required): The latitude of the service location is the same as when requesting this API `GET /api/General/Location/GetLocationAdvance`, don't use current location always.
- `BookingDate` (string, required): The date for booking the service in `YYYY-MM-DD` format.
- `BookingHour` (integer, required): The hour for booking the service (24-hour format).
- `BookingMinutes` (string, required): The minutes for booking the service.
- `ProviderUserID` (integer, required): The user ID of the service provider.
- `ProviderBranchID` (integer, required): The branch ID of the service provider.
- `AreaId` (integer, required): The area ID where the service is requested.
- `Address` (object, required): The address details where the service is requested, containing:
  - `address_type_id` (integer, required): The address type ID, `1` for home, `2` for work, `3` for friend home, `10` for other, check here `GET /api/General/AddressTypes`, So when customer select save location you have to pass address type id, otherwise pass `10`.
  - `city_id` (integer, required): The city ID from `GET /api/General/Location/GetLocationAdvance`.
  - `zone_id` (integer, required): The zone ID from `GET /api/General/Location/GetLocationAdvance`.
  - `area_id` (integer, required): The area ID from `GET /api/General/Location/GetLocationAdvance`, parameter called `id`.
  - `lat` (string, required): Latitude of the address, same as Lat above.
  - `lng` (string, required): Longitude of the address, same as Lng above.
  - `loc_desc` (string, optional): Description of the location.
- `Products` (array of objects, required): List of products associated with the order, this data comes when `POST /api/General/Services/Request/Providers` so you have to take it when requesting providers and pass it here, each product containing:
  - `id` (integer, required): Product ID.
  - `qty` (integer, required): Quantity of the product.
  - `total` (number, required): Total price of the product.
  - `UnitPrc` (number, required): Unit price of the product.
  - `PrdctBrandID` (integer, optional): Product brand ID.
  - `PrdctBrand` (string, optional): Product brand name.
  - `PrdctOrigin` (string, optional): Product origin.
  - `PrdctGuarantee` (string, optional): Product guarantee.
  - `PrdctFullSize` (string, optional): Full size of the product.
  - `PrdctPayloadSmbl` (string, optional): Payload symbol of the product.
  - `PrdtcName` (string, required): Name of the product.
  - `IsServiceFees` (boolean, required): Indicates if the item is a service fee.
- `CouponId` (integer, optional): Coupon ID for any discounts, when validating coupon by name you will get coupon id.
- `Notes` (string, optional): Additional notes or comments.
- `BrandId` (integer, optional): Brand ID.
- `Is_prepaid` (boolean, optional): Indicates if the service is prepaid.
- `IsPickup` (boolean or null, optional): Indicates if pickup is required this for a new service called shipping .
- `attached_images` (array of objects, optional): List of attached images, List of `string` refers to a binary image.

**Request Example**:
```json
{
    "MasterServiceID": 4,
    "ProviderID": 10031,
    "CarID": 18871,
    "Lng": 46.62729,
    "Lat": 24.689679,
    "BookingDate": "2024-06-22",
    "BookingHour": 1,
    "BookingMinutes": "30",
    "ProviderUserID": 20206,
    "ProviderBranchID": 82,
    "AreaId": 41,
    "Address": {
        "address_type_id": 10,
        "city_id": 1,
        "zone_id": 13,
        "area_id": 41,
        "lat": "24.689679",
        "lng": "46.62729",
        "loc_desc": ""
    },
    "Products": [
        {
            "id": 65,
            "qty": 1,
            "total": 1,
            "UnitPrc": 1,
            "PrdctBrandID": 0,
            "PrdctBrand": null,
            "PrdctOrigin": null,
            "PrdctGuarantee": null,
            "PrdctFullSize": null,
            "PrdctPayloadSmbl": null,
            "PrdtcName": "غسيل بلس خارجي ",
            "IsServiceFees": false
        },
        {
            "id": 0,
            "qty": 1,
            "total": 50,
            "UnitPrc": 50,
            "PrdctBrandID": 0,
            "PrdctBrand": null,
            "PrdctOrigin": null,
            "PrdctGuarantee": null,
            "PrdctFullSize": null,
            "PrdctPayloadSmbl": null,
            "PrdtcName": "غسيل سيارة",
            "IsServiceFees": true
        }
    ],
    "CouponId": 78,
    "Notes": "My Comment",
    "BrandId": 29,
    "Is_prepaid": true,
    "IsPickup": null,
    "attached_images": []
}
```

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (int): The ID of the newly added Order Request.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": 19599
}
```