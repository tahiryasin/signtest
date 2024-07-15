Here is the JSON API structure, including the correct answer in the questions list so that the app can determine if the chosen answer is correct without making additional API calls.

### 1. API Structure

#### 1.1 Fetch Test Categories

**Endpoint:** `GET /api/categories`

**Response:**
```json
{
  "categories": [
    {
      "id": 1,
      "name": "Motorcar/Jeep Test"
    },
    {
      "id": 2,
      "name": "Motorcycle Test"
    },
    {
      "id": 3,
      "name": "LTV Test"
    },
    {
      "id": 4,
      "name": "HTV Test"
    }
  ]
}
```

#### 1.2 Fetch Questions for a Category

**Endpoint:** `GET /api/categories/{categoryId}/questions`

**Response:**
```json
{
  "categoryId": 1,
  "questions": [
    {
      "id": 101,
      "text": "What does this traffic sign mean?",
      "image": "https://example.com/signs/sign1.png",
      "choices": [
        { "id": 1, "text": "Stop" },
        { "id": 2, "text": "Yield" },
        { "id": 3, "text": "No Entry" },
        { "id": 4, "text": "Speed Limit" }
      ],
      "correctChoiceId": 1
    },
    {
      "id": 102,
      "text": "What should you do at a yellow light?",
      "image": null,
      "choices": [
        { "id": 1, "text": "Speed up" },
        { "id": 2, "text": "Slow down and prepare to stop" },
        { "id": 3, "text": "Continue driving" }
      ],
      "correctChoiceId": 2
    },
    // ... 28 more questions
  ]
}
```

### 2. Detailed API Endpoints

#### 2.1 Fetch Test Categories
- **Description:** Get the list of test categories.
- **Method:** `GET`
- **Endpoint:** `/api/categories`
- **Response:**
  ```json
  {
    "categories": [
      {
        "id": 1,
        "name": "Motorcar/Jeep Test"
      },
      {
        "id": 2,
        "name": "Motorcycle Test"
      },
      {
        "id": 3,
        "name": "LTV Test"
      },
      {
        "id": 4,
        "name": "HTV Test"
      }
    ]
  }
  ```

#### 2.2 Fetch Questions for a Category
- **Description:** Get a list of 30 questions for the selected category.
- **Method:** `GET`
- **Endpoint:** `/api/categories/{categoryId}/questions`
- **Response:**
  ```json
  {
    "categoryId": 1,
    "questions": [
      {
        "id": 101,
        "text": "What does this traffic sign mean?",
        "image": "https://example.com/signs/sign1.png",
        "choices": [
          { "id": 1, "text": "Stop" },
          { "id": 2, "text": "Yield" },
          { "id": 3, "text": "No Entry" },
          { "id": 4, "text": "Speed Limit" }
        ],
        "correctChoiceId": 1
      },
      {
        "id": 102,
        "text": "What should you do at a yellow light?",
        "image": null,
        "choices": [
          { "id": 1, "text": "Speed up" },
          { "id": 2, "text": "Slow down and prepare to stop" },
          { "id": 3, "text": "Continue driving" }
        ],
        "correctChoiceId": 2
      },
      // ... 28 more questions
    ]
  }
  ```

In this revised structure, the `correctChoiceId` field is included in each question object. This allows the app to immediately determine if the selected answer is correct and provide instant feedback by showing red or green based on the user's choice.

This approach ensures that the app can handle the logic for verifying answers and transitioning to the next question without needing to make additional API calls for each answer submitted.
