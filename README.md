# text-structura
[![PyPI version](https://badge.fury.io/py/text-structura.svg)](https://badge.fury.io/py/text-structura)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Downloads](https://static.pepy.tech/badge/text-structura)](https://pepy.tech/project/text-structura)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue)](https://www.linkedin.com/in/eugene-evstafev-716669181/)


A Python package that takes user-provided text input and returns structured, validated output using pattern matching to ensure consistent formatting.

## Features

- Processes text from various sources like documents or audio transcripts
- Applies a system prompt to guide the LLM and a human message to frame the query
- Uses regex patterns to extract key information reliably
- Ideal for tasks like summarizing content, categorizing feedback, or generating standardized reports
- Does not rely on markdown or HTML formatting

## Installation

```bash
pip install text_structura
```

## Usage

```python
from text_structura import text_structura

response = text_structura("Your text input here")
```

### Using a Custom LLM

You can use your own LLM instance by passing it to the function:

```python
from langchain_openai import ChatOpenAI
from text_structura import text_structura

llm = ChatOpenAI()
response = text_structura("Your text input here", llm=llm)
```

### Using LLM7 with API Key

You can pass your LLM7 API key directly:

```python
from text_structura import text_structura

response = text_structura("Your text input here", api_key="your_api_key")
```

Or by setting the `LLM7_API_KEY` environment variable. You can obtain a free API key by registering at [https://token.llm7.io/](https://token.llm7.io/).

## Parameters

- `user_input` (str): The user input text to process
- `llm` (Optional[BaseChatModel]): The langchain LLM instance to use. Defaults to `ChatLLM7`.
- `api_key` (Optional[str]): The API key for LLM7. If not provided, the default `ChatLLM7` will be used.

## Default LLM

The package uses `ChatLLM7` from `langchain_llm7` by default. You can find more information about `ChatLLM7` [here](https://pypi.org/project/langchain-llm7/).

## Rate Limits

The default rate limits for LLM7 free tier are sufficient for most use cases of this package. If you want higher rate limits, you can pass your own API key via the `api_key` parameter or by setting the `LLM7_API_KEY` environment variable.

## Contributing

Contributions are welcome! Please refer to the issue tracker for potential areas of improvement.

## Author

* **Eugene Evstafev** - [hi@euegne.plus](mailto:hi@euegne.plus)

## GitHub

* **Project Repository:** [https://github.com/chigwell/text-structura](https://github.com/chigwell/text-structura)
* **Submit Issues:** [https://github.com/chigwell/text-structura/issues](https://github.com/chigwell/text-structura/issues)
* **GitHub Nickname:** chigwell