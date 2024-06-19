### Get Orders to Evaluate

**Endpoint**: `POST /api/Customer/Evaluations/OrdersToEvaulate`

**Description**: Retrieves orders that require evaluation by the customer.

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): An array containing orders to evaluate.
  - `reqeust_id` (integer): The ID of the order request.
  - `request_provider_id` (integer): The ID of the service provider.
  - `request_provider_name` (string): The name of the service provider.
  - `request_provider_eng_name` (string): The English name of the service provider.
  - `request_master_serivce_id` (integer): The ID of the master service.
  - `request_master_serivce_name` (string): The name of the master service.
  - `request_master_serivce_eng_name` (string): The English name of the master service.
  - `evaluation_id` (integer): The ID of the evaluation.
  - `evaluation_title` (string): The title of the evaluation.
  - `evaluation_eng_title` (string): The English title of the evaluation.
  - `evaluation_questions` (array): An array of evaluation questions.
    - `id` (integer): The ID of the evaluation question.
    - `name` (string): The name of the evaluation question.
    - `eng_name` (string): The English name of the evaluation question.
    - `order_no` (integer): The order number of the question.
  - `request_master_serivce_image` (string): URL for the master service image.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "reqeust_id": 16967,
      "request_provider_id": 10031,
      "request_provider_name": "sayaratech",
      "request_provider_eng_name": "sayaratech",
      "request_master_serivce_id": 3,
      "request_master_serivce_name": "تبديل الكفرات ",
      "request_master_serivce_eng_name": "Tires Services",
      "evaluation_id": 1,
      "evaluation_title": "تقيم الخدمة المقدمة",
      "evaluation_eng_title": "rate service ",
      "evaluation_questions": [
        {
          "id": 3,
          "name": "هل تنصح اصدقائك بتطبيق سيارة تك ",
          "eng_name": "service",
          "order_no": 1
        },
        {
          "id": 2,
          "name": "كيف اداء الفني ",
          "eng_name": "test tsettest tsettest tsettest tset",
          "order_no": 2
        },
        {
          "id": 1,
          "name": "كيف سرعة الخدمة ",
          "eng_name": "speed ",
          "order_no": 3
        }
      ],
      "request_master_serivce_image": null
    }
  ]
}
```