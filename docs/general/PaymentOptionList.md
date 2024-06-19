## General Endpoints

### Get Payments Option List

**Endpoint**: `GET /api/General/PyamentsOptionList`

**Description**: This endpoint retrieves a list of payment options available for the services.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array of payment options, where each object contains:
  - `id` (int): The identifier for the payment option.
  - `name` (string): The name of the payment option in Arabic.
  - `eng_name` (string): The name of the payment option in English.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": -1,
      "name": "غير متوفر",
      "eng_name": "NA"
    },
    {
      "id": 0,
      "name": "من المحفظه",
      "eng_name": "From Wallet"
    },
    {
      "id": 1,
      "name": "كاش",
      "eng_name": "Cash"
    },
    {
      "id": 2,
      "name": "اون لاين",
      "eng_name": "Online"
    },
    {
      "id": 3,
      "name": "كاش ومحفظة",
      "eng_name": "Cash And Wallet"
    },
    {
      "id": 4,
      "name": "اون لاين ومحفظة",
      "eng_name": "Online And Wallet"
    },
    {
      "id": 5,
      "name": "من اشتراك الباقة",
      "eng_name": "From Package Subscription"
    }
  ]
}
