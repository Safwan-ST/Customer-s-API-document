# Battery Service API Documentation

This document outlines the flow for using the Battery Service APIs, including searching for batteries by brand or size, selecting products, and placing service requests.

## 1. Search for Battery by Brand or Size

### Search by Brand

#### Endpoint
`GET /api/General/Services/Products/Brands/{id}`

#### Description
Fetches all the brands for a specified master service, including their IDs, names, and descriptions. [Full_Details](1-1FindTheBrands.md)

#### Request Parameters
- `id` (required): The ID of the master service.

#### Response Parameters
- `Data`: An array of brand objects containing:
  - `id`: The ID of the brand.
  - `name`: The name of the brand.
  - `description`: The description of the brand.
  - `...`

### Search by Size

#### Endpoint
`GET /api/General/Services/Spesifications/List`

#### Description
Fetches all available specifications for batteries. [Full_Details](1-2FindTheSizes.md)

#### Response Parameters
- `Data`: An array of specification objects containing:
  - `id`: The ID of the specification.
  - `name`: The name of the specification.
  - `...`

## 2. Retrieve Products

### Endpoint
`GET /api/General/Services/Products/List`

### Description
Fetches all products that match the provided filters (brand ID, size ID, or both). [Full_Details](../2GetTheProducts.md)

### Request Parameters
- `brand_id` (optional): The ID of the selected brand.
- `size_id` (optional): The ID of the selected size.

### Response Parameters
- `Data`: An array of product objects containing:
  - `id`: The ID of the product.
  - `name`: The name of the product.
  - `description`: The description of the product.
  - `binary_image`: The binary image of the product.
  - `...`

## 3. Retrieve Available Providers

### Endpoint
`POST /api/General/Services/Request/Providers`

### Description
Fetches available providers for the selected product. [Full_Details](../../GetProviders.md)

### Request Body Parameters
- `[id]` (required): List of the selected products.

### Response Parameters
- `Data`: An array of provider objects.

## 4. Pick Schedule for the Service

### Endpoint
`POST /api/General/Services/Request/PickScheduleService`

### Description
Selects the schedule for the service request if the `allow_appointment` parameter is `true`. [Full_Details](../../PickScheduele.md)

### Request Body Parameters
- Various parameters required for scheduling the service (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains details of the selected schedule.

## 5. Confirm Service Request

### Endpoint
`POST /api/Customer/Orders/AddNewRequest`

### Description
Confirms and creates a new service request. [Full_Details](../../customer/Orders/AddNewOrder.md)

### Request Body Parameters
- Various parameters required for creating the service request (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains the ID of the newly created request.

## Important Parameters in Master Services Object

### `allow_appointment`
- If `true`, proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.

### `force_advance_payment`
- If `true`, show payment options to the customer after creating the order. If the customer does not pay, display a message indicating that the order is not confirmed yet.


## Flow Summary

1. **Search for Battery**:
   - By Brand: Use `GET /api/General/Services/Products/Brands/{id}` to get brands for the master service.
   - By Size: Use `GET /api/General/Services/Spesifications/List` to get specifications for batteries.
2. **Retrieve Products**: Use `GET /api/General/Services/Products/List` to get products that match the provided filters.
3. **Retrieve Providers**: Use `POST /api/General/Services/Request/Providers` to get available providers for the selected product.
4. **Check Appointment Requirement**: If `allow_appointment` is `true`, proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.
5. **Confirm Service Request**: Use `POST /api/Customer/Orders/AddNewRequest` to confirm and create the service request.
