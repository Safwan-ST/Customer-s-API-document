# Oil Service API Documentation

This document outlines the flow for using the Oil Service APIs, including retrieving available filters, selecting oil brands, finding providers, and placing service requests.

## 1. Retrieve Available Filters

### Endpoint
`GET /api/General/Services/Products/Filters/{id}`

### Description
Retrieves available filters for the oil service identified by `{id}`. [Full_Details](1FindTheFilters.md)

### Request Parameters
- `id` (required): The ID of the oil service.

### Response Parameters
- `Data`: An array of filter objects containing:
  - `id`: The ID of the filter.
  - `name`: The name of the filter.
  - `...`

## 2. Retrieve Oil Brands

### Endpoint
`GET /api/General/Services/Products/Brands/{id}`

### Description
Fetches all the brands for a specified oil service, including their IDs, names, and descriptions. [Full_Details](2FindBrandsForFilters.md)

### Request Parameters
- `id` (required): The ID of the oil service.

### Response Parameters
- `Data`: An array of brand objects containing:
  - `id`: The ID of the brand.
  - `name`: The name of the brand.
  - `...`


## 3. Retrieve Products

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

## 4. Retrieve Available Providers

### Endpoint
`POST /api/General/Services/Request/Providers`

### Description
Fetches available providers for the selected oil filter and brand. [Full_Details](../../GetProviders.md)

### Request Body Parameters
- `[id]` (required): List of the selected products. You must pass also the id of the selected filters from step 1

### Response Parameters
- `Data`: An array of provider objects.

## 5. Pick Schedule for the Service

### Endpoint
`POST /api/General/Services/Request/PickScheduleService`

### Description
Selects the schedule for the service request if the `allow_appointment` parameter is `true`. [Full_Details](../../PickScheduele.md)

### Request Body Parameters
- Various parameters required for scheduling the service (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains details of the selected schedule.

## 6. Confirm Service Request

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

## Flow Summary

1. **Retrieve Available Filters**:
   - Use `GET /api/General/Services/Products/Filters/{id}` to get available filters for the oil service.
2. **Retrieve Oil Brands**:
   - Use `GET /api/General/Services/Products/Brands/{id}` to get brands for the oil service.
3. **Retrieve Products**: Use `GET /api/General/Services/Products/List` to get products that match the provided filters.
4. **Retrieve Providers**:
   - Use `POST /api/General/Services/Request/Providers` to get available providers for the selected filter and brand.
5. **Check Appointment Requirement**:
   - If `allow_appointment` is `true`, proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.
6. **Confirm Service Request**:
   - Use `POST /api/Customer/Orders/AddNewRequest` to confirm and create the service request.
