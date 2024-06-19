## General Endpoints

### Get Products for the Service

#### Endpoint: `GET /api/General/Services/Products/List`

Retrieves products for a service based on various filters such as brand, size, product name, etc.

**Request Parameters**:
- `MasterServiceID` (int): The identifier of the master service.
- `PageIndex` (int): The page index for pagination.
- `PageSize` (int): The number of items per page.
- `Width` (int, optional): The width of the product.
- `Height` (int, optional): The height of the product.
- `Size` (int, optional): The size of the product.
- `BrandID` (int, optional): The identifier of the brand for filtering products.
- `ProductName` (string, optional): The name of the product for filtering.
- `CarModelID` (int, optional): The identifier of the car model related to the product.
- `Recommened` (boolean, optional): Indicates if the product is recommended.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): An object containing a list of products.
  - `List` (array): An array of products, where each object contains:
    - `id` (int): The identifier of the product.
    - `name` (string): The name of the product in Arabic.
    - `eng_name` (string): The name of the product in English.
    - `price` (float): The price of the product.
    - `desc` (string, nullable): Description of the product in Arabic.
    - `eng_desc` (string, nullable): Description of the product in English.
    - `Size` (string, nullable): The size of the product.
    - `FullSize` (string, nullable): Full size description of the product.
    - `Width` (string, nullable): The width of the product.
    - `Height` (string, nullable): The height of the product.
    - `Origin` (string, nullable): The origin of the product.
    - `Guarantee` (string): The guarantee period of the product.
    - `Speed_And_Arithmetic` (string, nullable): Speed and arithmetic details.
    - `RecommenedValue` (string, nullable): Recommended value of the product.
    - `binary_image` (string): Base64 encoded binary image of the product.
    - `service_brand_id` (int): The identifier of the brand associated with the product.
    - `brand_name` (string): The name of the brand in Arabic.
    - `brand_eng_name` (string): The name of the brand in English.
    - `manufacture_year` (string): The manufacture year of the product.

**Example Link**: [Example API Link](https://satc.live/api/General/Services/Products/List?MasterServiceID=3&PageIndex=1&PageSize=10&Width=205&Height=65&Size=16&BrandID=17&ProductName=New%20Hankook&CarModelID=101&Recommened=true)

**response example:**
```json
{
    "status": true,
    "message": "تمت العمليه بنجاح",
    "error": "",
    "Data": {
        "List": [
            {
                "id": 10137,
                "name": "٨٠",
                "eng_name": "New Hankook",
                "price": 555,
                "desc": null,
                "eng_desc": null,
                "Size": "٨٠",
                "FullSize": null,
                "Width": null,
                "Height": null,
                "Origin": null,
                "Guarantee": "1",
                "Speed_And_Arithmetic": null,
                "RecommenedValue": "٨٠",
                "binary_image": "",
                "service_brand_id": 17,
                "brand_name": "هانكوك",
                "brand_eng_name": "Hankook",
                "manufacture_year": "2023"
            }
        ]
    }
}
```

**Now you can go to the `POST /api/General/Services/Request/Providers` API**
