# AI Website Summarizer

Give it any webpage URL, and it reads the page and generates a clear, concise summary.

## How It Works

The application has three main components.

### Step 1: Extract Website Content (Web Scraping)

The first step extracts readable text from a webpage.

You don't need to understand every line of the scraping code to get started. A Python library called **BeautifulSoup** helps parse HTML and extract text.

The process is simple:

1. Accept a website URL.
2. Fetch the webpage content.
3. Remove unnecessary HTML elements.
4. Extract the page title and readable text.

**Input:** Website URL  
**Output:** Webpage title and readable text

This step uses traditional web scraping, not AI.

### Step 2: Generate the Summary (Prompt + LLM)

This is where the AI comes in.

The extracted webpage content is passed to a Large Language Model (LLM) using the OpenAI API.

The model processes the content and generates a clear, concise summary that highlights the main points.

**Input:** Extracted webpage text  
**Output:** AI-generated summary

### Step 3: Build the Web Interface (Gradio)

The application uses **Gradio** to provide a simple web interface.

Users can enter a website URL and view the generated summary without interacting directly with the Python code.

The interface includes:
- A text box for entering the website URL.
- A summary area to display the result.
- A simple interface for easy interaction.

## Technologies Used

- **Python** — Application logic
- **Requests** — Fetch webpage content
- **BeautifulSoup** — Parse HTML and extract text
- **OpenAI API** — Generate summaries using an LLM
- **Gradio** — Build the web interface

## Getting Started

### Prerequisites

- Python 3 installed
- An OpenAI API key

### Step 1: Install Dependencies

Run the following command in your terminal:

```bash
pip install openai gradio requests beautifulsoup4 python-dotenv
```

### Step 2: Configure Your API Key

Create a `.env` file in the project root directory and add your OpenAI API key:

```env
OPENAI_API_KEY=your_openai_api_key
```

Replace `your_openai_api_key` with your actual API key.

**Security note:** Never commit your `.env` file or expose your API key in your source code.

### Step 3: Launch the Application

Run:

```bash
python app.py
```

If your Mac uses `python3` instead of `python`, run:

```bash
python3 app.py
```

### Step 4: Open the Application

Gradio will display a local URL in your terminal, similar to:

```text
Running on local URL: http://127.0.0.1:7860
```

Open this URL in your browser to use the application.

If you enable Gradio's `share=True` option, it may also generate a public URL:

```text
Running on public URL: https://example.gradio.live
```

You can share that link with others while the application is running. Avoid using public sharing for sensitive data, and remember that the link may allow other people to access your application.

## Project Workflow

```text
Website URL
    |
    v
Fetch Webpage
    |
    v
Extract Readable Text
    |
    v
Send Content to LLM
    |
    v
Generate Summary
    |
    v
Display Summary in Gradio
```
