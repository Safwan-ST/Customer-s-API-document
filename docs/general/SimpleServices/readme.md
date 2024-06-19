# Simple Services API Documentation

This document outlines the flow for using various Simple Services APIs, including retrieving brands, selecting items, and placing service requests.

## 1. Retrieve Brands for a Master Service

### Endpoint
`GET /api/General/Services/Products/Brands/{id}`

### Description
Fetches all the brands for a specified master service, including their IDs, names, and descriptions. [Full_Details](docs/general/SimpleServices/Brands.md)

### Request Parameters
- `id` (required): The ID of the master service.

### Response Parameters
- `Data`: An array of brand objects containing:
  - `id`: The ID of the brand.
  - `name`: The name of the brand.
  - `description`: The description of the brand.
  - `...`

## 2. Retrieve Items for a Brand

### Endpoint
`GET /api/General/Services/Products/ItemsByBrand/{id}`

### Description
Fetches all items for a specified brand, including their IDs, names, descriptions, and binary images.

### Request Parameters
- `id` (required): The ID of the brand.

### Response Parameters
- `Data`: An array of item objects containing:
  - `id`: The ID of the item.
  - `name`: The name of the item.
  - `description`: The description of the item.
  - `binary_image`: The binary image of the item.
  - `...`

## 3. Retrieve Available Providers

### Endpoint
`POST /api/General/Services/Request/Providers`

### Description
Fetches available providers for a selected item. after choosing the provider check if `allow_appointment` is `true`, if true then proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.

### Request Body Parameters
- `[id]` (required): List of the selected items.

### Response Parameters
- `Data`: An array of provider objects.

## 4. Pick Schedule for the Service

### Endpoint
`POST /api/General/Services/Request/PickScheduleService`

### Description
Selects the schedule for the service request.

### Request Body Parameters
- Various parameters required for scheduling the service (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains details of the selected schedule.

## 5. Confirm Service Request

### Endpoint
`POST /api/Customer/Orders/AddNewRequest`

### Description
Confirms and creates a new service request.

### Request Body Parameters
- Various parameters required for creating the service request (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains the ID of the newly created request.

## Important Parameters in Master Services Object

### `force_advance_payment`
- If `true`, show payment options to the customer after creating the order. If the customer does not pay, display a message indicating that the order is not confirmed yet.

### `is_required_attachments_on_new_request`
- If `true`, request images from the customer using the camera or gallery.

## Flow Summary

1. **Retrieve Brands**: Use `GET /api/General/Services/Products/Brands/{id}` to get brands for the master service.
2. **Retrieve Items**: Use `GET /api/General/Services/Products/ItemsByBrand/{id}` to get items for the selected brand.
3. **Retrieve Providers**: Use `POST /api/General/Services/Request/Providers` to get available providers for the selected item.
4. **Check Appointment Requirement**: If `allow_appointment` is `true`, proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.
5. **Confirm Service Request**: Use `POST /api/Customer/Orders/AddNewRequest` to confirm and create the service request.
6. **Payment and Attachments**: Based on the `force_advance_payment` and `is_required_attachments_on_new_request` parameters, handle payment and request any necessary attachments from the customer.
