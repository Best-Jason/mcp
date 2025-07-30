# MCP Server with File System & API Tools

> A simple, command-line based MCP (Meta-Cognitive Prompting) server built in Python. This project demonstrates how to create and expose custom tools for file system interaction and external API calls.

This server runs locally and listens for JSON commands via standard input/output (`stdio`). It was developed as an exercise to understand the fundamentals of building extensible AI tooling backends.

## Features

This server comes with several pre-built tools:

*   👋 `say_hello`: A simple tool to demonstrate basic functionality.
*   📂 `list_directory`: Lists the names of all files and folders within a specified directory.
*   ☀️ `get_weather`: Fetches the current weather for any location by calling the public `wttr.in` API.

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### Prerequisites

You need to have Python and pip installed on your system.
*   Python 3.8+
*   `pip` (usually comes with Python)

### Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```

2.  **Create and activate a virtual environment (Recommended):**
    *   On Windows:
        ```sh
        python -m venv venv
        .\venv\Scripts\activate
        ```
    *   On macOS/Linux:
        ```sh
        python3 -m venv venv
        source venv/bin/activate
        ```

3.  **Install the required packages:**
    Create a file named `requirements.txt` and add the following:
    ```
    fastmcp
    requests
    ```
    Then, install the packages:
    ```sh
    pip install -r requirements.txt
    ```

## Usage

1.  **Start the MCP Server:**
    ```sh
    python my_mcp_server.py
    ```

2.  **Interact with the Tools:**
    The server listens for single-line JSON commands.

    #### Example: List contents of the current directory
    ```json
    {"tool_name": "list_directory", "kwargs": {"directory_path": "."}}
    ```

    #### Example: Get the weather for a city
    ```json
    {"tool_name": "get_weather", "kwargs": {"location": "Tokyo"}}
    ```

## License

This project is licensed under the MIT License.

## Acknowledgements

*   This project was created by following a tutorial on building practical MCP tools.
*   Weather data provided by [wttr.in](https://wttr.in).