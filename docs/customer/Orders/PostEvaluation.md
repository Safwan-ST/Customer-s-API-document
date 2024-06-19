### Post Evaluation

**Endpoint**: `POST /api/Customer/Evaluations/PostEvaluation`

**Description**: Submits an evaluation for a specific order based on provided answers to evaluation questions.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Body Parameters**:
- `evaluation_id` (integer, required): The ID of the evaluation template.
- `request_id` (integer, required): The ID of the order request being evaluated.
- `answers` (array, required): An array of objects containing evaluation question IDs and their corresponding answers.
  - `question_id` (integer): The ID of the evaluation question.
  - `anwser_rate` (integer): The rating given to the question (typically on a scale of 1-5).
- `note` (string): Additional comments or notes provided by the customer.

**Request Body Example**:
```json
{
    "evaluation_id": 1,
    "request_id": 16967,
    "answers": [
        {
            "question_id": 3,
            "anwser_rate": 5
        },
        {
            "question_id": 2,
            "anwser_rate": 4
        },
        {
            "question_id": 1,
            "anwser_rate": 5
        }
    ],
    "note": "comment custom"
}
```

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (null): No data is returned on successful deletion.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": null
}
```