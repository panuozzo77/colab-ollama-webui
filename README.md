# Ollama & Open WebUI in Google Colab

This repository provides a streamlined setup for running [Ollama](https://ollama.com/) (a framework for running large language models locally) and [Open WebUI](https://github.com/open-webui/open-webui) (a user-friendly interface for interacting with LLMs) within a Google Colab environment.  This allows you to experiment with LLMs without needing a powerful local machine.  It also features automatic synchronization with your Google Drive for persistent storage of your data.

## Features

*   **Easy Setup:**  Simple installation and configuration using Google Colab.
*   **Ollama Integration:** Runs Ollama in the background, allowing you to serve and interact with various language models.
*   **Open WebUI:** Provides a web-based interface to chat with and manage your Ollama models.
*   **Google Drive Persistence:** Automatically saves your Open WebUI data (chat history, settings, etc.) to your Google Drive, so you don't lose progress between Colab sessions.
*   **Periodic Data Synchronization:** Keeps your local data and Google Drive data in sync with scheduled backups.
*   **Manual Save Option:** Includes a cell for manual saving of all data to Google Drive on demand.

## Prerequisites

*   A Google account (for Google Colab and Google Drive).

## Setup Instructions

1.  **Open in Google Colab:** Click the "Open in Colab" button (if available) or create a new Colab notebook and copy the code from the `ollama_webui.ipynb` file into it.  (The link in the search results points to such a notebook).

    [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/panuozzo77/colab-ollama-webui/blob/main/ollama_webui.ipynb)

2. **Choose the model in the 2th cell**
3. **Execute all the cells except this one at the bottom:**

    ```
    !ln -s /content/venv/lib/python3.11/site-packages/open_webui/data /content/drive/MyDrive/OpenWebUI_Data
    ```

4.  **Start Servers and Data Synchronization:** when you're ready, run this cell:
    ```
    !ln -s /content/venv/lib/python3.11/site-packages/open_webui/data /content/drive/MyDrive/OpenWebUI_Data
    ```
    This will:
    *   Starts the Ollama server in a background thread.
    *   Starts the Open WebUI server in a background thread.
    *   Checks if data exists in your Google Drive and pulls it to the Colab environment if found.
    *   Starts a background thread that periodically saves data from the Colab environment to your Google Drive.
    *   Generate the url for accessing the webUI. It will be something like: http://rnhmq-34-16-223-215.a.free.pinggy.link/

Enjoy
