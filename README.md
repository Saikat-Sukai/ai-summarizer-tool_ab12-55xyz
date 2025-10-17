# FastAPI Text Summarization

## Summary

This project provides a FastAPI application with an endpoint `/summarize` that takes a block of text as input and returns a summarized version using the OpenAI API. The application is designed to be simple to set up and use, allowing users to quickly obtain concise summaries of larger texts.

## Setup & Usage Instructions

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)
- An OpenAI API key

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/fastapi-text-summarization.git
   cd fastapi-text-summarization
   ```

2. Create a virtual environment (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Set your OpenAI API key as an environment variable:

   ```bash
   export OPENAI_API_KEY='your_openai_api_key'  # On Windows use `set OPENAI_API_KEY=your_openai_api_key`
   ```

### Running the Application

To start the FastAPI server, run the following command:

```bash
uvicorn main:app --reload
```

The application will be accessible at `http://127.0.0.1:8000`.

### Example API Calls

You can use tools like `curl`, Postman, or any HTTP client to make requests to the API. Below are some example calls:

#### Example 1: Summarizing a Short Text

```bash
curl -X POST "http://127.0.0.1:8000/summarize" -H "Content-Type: application/json" -d '{"text": "FastAPI is a modern web framework for building APIs with Python 3.7+ based on standard Python type hints."}'
```

**Response:**

```json
{
  "summary": "FastAPI is a modern web framework for building APIs with Python."
}
```

#### Example 2: Summarizing a Longer Text

```bash
curl -X POST "http://127.0.0.1:8000/summarize" -H "Content-Type: application/json" -d '{"text": "OpenAI has developed several powerful AI models, including GPT-3, which can generate human-like text based on a given prompt. These models have applications in various fields, including natural language processing, content creation, and more."}'
```

**Response:**

```json
{
  "summary": "OpenAI's GPT-3 can generate human-like text for various applications."
}
```

#### Example 3: Summarizing a News Article

```bash
curl -X POST "http://127.0.0.1:8000/summarize" -H "Content-Type: application/json" -d '{"text": "In recent news, scientists have made significant advancements in renewable energy technologies, which could lead to a more sustainable future. These innovations aim to reduce carbon emissions and combat climate change."}'
```

**Response:**

```json
{
  "summary": "Scientists have advanced renewable energy technologies for a sustainable future."
}
```

## Explanation of Key Files

- **main.py**: The main application file where the FastAPI app is created and the `/summarize` endpoint is defined.
- **requirements.txt**: A file listing the dependencies required to run the application, including FastAPI and the OpenAI library.
- **README.md**: This documentation file, providing an overview of the project, setup instructions, and usage examples.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.