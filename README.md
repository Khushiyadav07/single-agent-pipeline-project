# single-agent-pipeline-project

# Single Agent Smart Assistant

## Overview

This project is a simple **Single-Agent Smart Assistant** built using Python. The main purpose of the project is to understand a user's query and decide what type of task needs to be performed.

The agent uses conditional routing to handle different types of queries. Based on the query, it can perform a calculation, extract keywords from text, or provide a general response.

## Features

The assistant can handle the following tasks:

* Perform basic mathematical calculations
* Extract keywords from a given sentence
* Handle general queries
* Return results in a structured format
* Handle basic errors such as empty queries or invalid calculations
* Provide an interactive mode for testing different queries

## How the Agent Works

The agent first converts the user's query into lowercase and checks the intent of the query.

The routing works as follows:

* If the query contains **"calculate"**, it is sent to the Calculator Tool.
* If the query contains **"keywords"**, it is sent to the Keyword Extractor Tool.
* If neither condition is matched, the query is treated as a general query.

The overall flow is:

```text
User Query
    |
    v
Check Query Intent
    |
    +---- "calculate" ----> Calculator Tool
    |
    +---- "keywords" -----> Keyword Extractor
    |
    +---- Other Query -----> General Response
    |
    v
Structured Output
```

## Tools Used

### 1. Calculator Tool

The Calculator Tool evaluates mathematical expressions provided by the user.

Example:

```text
Calculate 20 + 5
```

Output:

```python
{
    "type": "calculation",
    "result": "25"
}
```

### 2. Keyword Extractor Tool

The Keyword Extractor takes a sentence and identifies words that can be treated as keywords.

Example:

```text
Extract keywords from Artificial Intelligence is transforming industries
```

The tool returns a list of keywords from the given text.

### 3. General Query Handling

If the query does not match the calculation or keyword extraction conditions, the agent handles it as a general query.

Example:

```text
What is machine learning?
```

Output format:

```python
{
    "type": "general",
    "result": "You asked: What is machine learning?"
}
```

## Expected Output Format

The agent returns the response in a structured dictionary format:

```python
{
    "type": "calculation / keywords / general / error",
    "result": ...
}
```

This makes it easier to understand which route was selected by the agent and what result was produced.

## Test Cases

The following queries were used to test the agent:

1. `Calculate 20 + 5`
2. `Extract keywords from Artificial Intelligence is transforming industries`
3. `What is machine learning?`

The agent correctly routes these queries to the appropriate handling logic.

## Interactive Mode

The project also includes an interactive mode where the user can enter queries continuously.

Example:

```text
Enter query (type 'exit' to stop): Calculate 100 / 4
```

The agent processes the query and displays the result.

The user can type:

```text
exit
```

to stop the interactive mode.

## Error Handling

Basic error handling has been included in the project. The agent can handle situations such as:

* Empty queries
* Missing mathematical expressions
* Invalid calculations
* Missing text for keyword extraction
* Unexpected errors during processing

In such cases, the agent returns an error type instead of stopping the entire program.

## Technologies Used

* Python
* Google Colab
* Python Functions
* Conditional Routing

## Project Structure

```text
Single-Agent-Smart-Assistant/
│
├── Copy_of_week_8_assignment.ipynb
└── README.md
```

## How to Run

1. Open the notebook in Google Colab.
2. Run the Calculator Tool cell.
3. Run the Keyword Extractor Tool cell.
4. Run the Agent Function cell.
5. Run the test cases.
6. Run the Interactive Mode cell to test your own queries.

## Conclusion

This project demonstrates the basic working of a single-agent system using conditional routing. The agent identifies the intent of a user query and directs it to the appropriate tool or response logic. It helped me understand the basics of **agent logic, routing, tool integration, structured outputs, and error handling**.
