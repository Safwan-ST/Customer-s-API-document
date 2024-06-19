## General Endpoints

### 13. Get Service Providers for Requests

**Endpoint**: `POST /api/General/Services/Request/Providers`

**Description**: Retrieves service providers based on the specified parameters and service type.

**Headers**:
- `authorization`: `Bearer {Token}` (Customer token)

**Request Parameters**:
- `MasterServiceID` (integer): ID of the master service.
- `AreaID` (integer): ID of the area where the service is requested.
- `CarModelID` (integer): ID of the car model.
- `CarVendorID` (integer): ID of the car vendor.
- `CarCylinderID` (integer): ID of the car cylinder.

**Request Body**:
- `[int Items IDs]`: Array of requested items IDs (Filters Products).

**Tires Provider Example**:
- Endpoint URL: `https://satc.live/api/General/Services/Request/Providers?MasterServiceID=3&AreaID=41&CarModelID=94&CarVendorID=3&CarCylinderID=147`
- Request Body: `[13564]`

**Oil Change Example**:
- Endpoint URL: `https://satc.live/api/General/Services/Request/Providers?MasterServiceID=5&AreaID=41&CarModelID=94&CarVendorID=3&CarCylinderID=147`
- Request Body: `[10056, 10057, 10058, 10094]`

**Battery Service Example**:
- Endpoint URL: `https://satc.live/api/General/Services/Request/Providers?MasterServiceID=2&AreaID=41&CarModelID=94&CarVendorID=3&CarCylinderID=147`
- Request Body: `[13228]`

**Car Wash and Other Services Example**:
- Endpoint URL: `https://satc.live/api/General/Services/Request/Providers?MasterServiceID=10022&AreaID=41&CarModelID=94&CarVendorID=3&CarCylinderID=147`
- Request Body: `[14000]`

### Response Parameters

The response contains the following parameters:

### Response Parameters

The response contains the following parameters:

- `status` (boolean): Indicates if the request was successful (`true`) or not (`false`).
- `message` (string): A message indicating the result of the operation.
- `error` (string): Any error message related to the operation, empty if no error occurred.
- `Data` (array): An array of provider and service item details.
    - `Provider` (object): Details of the service provider.
      - `id` (integer): Provider ID.
      - `name` (string): Provider name in Arabic.
      - `eng_name` (string): Provider name in English.
      - `logo_binary_image` (string or null): Binary image data of provider's logo, or null if not available.
      - `provider_service_images` (array): Array of images related to provider services.
      
    - `Items` (array): Array of service items.
      - `id` (integer): Item ID.
      - `qty` (integer): Quantity of the item.
      - `total` (float): Total cost of the item.
      - `UnitPrc` (float): Unit price of the item.
      - `tax` (float): Tax amount applicable to the item.
      - `totalBeforeTax` (float): Total cost before tax.
      - `PrdctBrandID` (integer): Brand ID of the product associated with the item.
      - `PrdctBrand` (string or null): Brand name of the product, or null if not available.
      - `PrdctOrigin` (string or null): Origin of the product, or null if not available.
      - `PrdctGuarantee` (string or null): Guarantee details of the product, or null if not available.
      - `PrdctFullSize` (string or null): Full size details of the product, or null if not available.
      - `PrdctPayloadSmbl` (string or null): Payload symbol of the product, or null if not available.
      - `PrdtcName` (string): Product name in Arabic.
      - `IsServiceFees` (boolean): Indicates if service fees are applicable for the item.

    - `AvgEvalulation` (float): Average evaluation score.
    - `ServiceDescription` (string or null): Description of the service, or null if not available.
    - `Total` (float): Total cost of all items including taxes.
    - `TotalBeforeTax` (float): Total cost of all items before applying taxes.
    - `Tax` (float): Total tax amount.
    - `is_include_in_my_packge` (boolean): Indicates if the service is included in a package.
    - `closest_booking_date` (array): Array of closest booking dates.
    - `evaluation_list` (array): Array of evaluations given by customers.
      - `creaetd_date` (string): Date and time when the evaluation was created.
      - `result` (float): Evaluation result.
      - `comment` (string): Comment provided with the evaluation.
      - `customer_name` (string): Customer name in Arabic.
      - `customer_eng_name` (string): Customer name in English.

**Response Example**:
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": [
        {
            "Provider": {
                "id": 10317,
                "name": "test222",
                "eng_name": "test222",
                "logo_binary_image": null,
                "provider_service_images": []
            },
            "Items": [
                {
                    "id": 14097,
                    "qty": 1,
                    "total": 450.00,
                    "UnitPrc": 450.00,
                    "tax": 58.70,
                    "totalBeforeTax": 391.3,
                    "PrdctBrandID": 0,
                    "PrdctBrand": null,
                    "PrdctOrigin": null,
                    "PrdctGuarantee": null,
                    "PrdctFullSize": null,
                    "PrdctPayloadSmbl": null,
                    "PrdtcName": "الباقة النصف سنوية لـ 24 طلبات لمدة 180 يوم",
                    "IsServiceFees": false
                }
            ],
            "AvgEvalulation": 4.880000,
            "ServiceDescription": null,
            "Total": 450.00,
            "TotalBeforeTax": 391.3,
            "Tax": 58.70,
            "is_include_in_my_packge": false,
            "closest_booking_date": [],
            "evaluation_list": [
                {
                    "creaetd_date": "2024-06-17T02:34:56.613",
                    "result": 5.00,
                    "comment": "",
                    "customer_name": "taimoor mayuser",
                    "customer_eng_name": "taimoor mayuser"
                },
                {
                    "creaetd_date": "2024-05-20T11:17:15.957",
                    "result": 5.00,
                    "comment": "",
                    "customer_name": "Elon Musk",
                    "customer_eng_name": "Elon Musk"
                },
                {
                    "creaetd_date": "2024-05-19T13:31:11.667",
                    "result": 5.00,
                    "comment": "",
                    "customer_name": "Elon Musk",
                    "customer_eng_name": "Elon Musk"
                },
                {
                    "creaetd_date": "2024-05-19T10:35:47.417",
                    "result": 5.00,
                    "comment": "",
                    "customer_name": "as dd",
                    "customer_eng_name": "as dd"
                },
                {
                    "creaetd_date": "2024-05-17T00:11:21.747",
                    "result": 5.00,
                    "comment": "",
                    "customer_name": "زياد ",
                    "customer_eng_name": "زياد "
                }
            ]
        }
    ]
}
```