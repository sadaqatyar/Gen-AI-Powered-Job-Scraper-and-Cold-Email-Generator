# AI-Powered Job Scraping, Matching, and Email Generation

This project showcases a streamlined workflow for:
1. Scraping job data from websites.
2. Extracting relevant information in structured JSON format.
3. Matching skills from job descriptions to a portfolio stored in a vector database.
4. Generating personalized cold emails tailored to the job description.

## Features

- **Web Scraping**: Extracts job-related information from career pages.
- **LLM Processing**: Uses Groq-powered LLaMA 3.1 for structured data extraction.
- **Vector Search**: Finds relevant portfolio links based on job skills.
- **Cold Email Generation**: Creates a professional cold email for business development.

## Tools and Technologies

- **LangChain**: To orchestrate LLM prompts and chains.
- **Groq API**: For utilizing advanced LLaMA models.
- **ChromaDB**: Persistent vector database for portfolio storage and search.
- **Pandas**: To manage and process portfolio data.
- **Python**: Core programming language.

## Prerequisites

- Python 3.8 or later
- Groq API key (sign up at [Groq](https://groq.com))
- Libraries: `langchain-groq`, `langchain-community`, `langchain-core`, `chromadb`, `pandas`

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/your-username/job-scraping-email.git
    cd job-scraping-email
    ```

2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Add your Groq API key:
    Update the `groq_api_key` in the script.

4. Prepare your portfolio data:
    - Save your portfolio details as `my_portfolio.csv` with the following columns:
        - `Techstack`: A brief description of your skills or technologies.
        - `Links`: URLs showcasing your work or projects.

## Usage

### 1. Web Scraping and Job Extraction
- Extract job data from a website using the `WebBaseLoader` and LangChain's Groq integration.
- The output will be a structured JSON object containing:
    - `role`
    - `experience`
    - `skills`
    - `description`

### 2. Skill Matching
- Skills from the extracted job description are matched with your portfolio stored in a **ChromaDB** vector database.

### 3. Email Generation
- A cold email is generated using a custom prompt. It highlights your portfolio and aligns AtliQ's capabilities with the client's requirements.

## Example Workflow

1. Run the script:
    ```python
    python main.py
    ```
2. The pipeline performs:
    - Scraping job data.
    - Matching job skills to portfolio items.
    - Generating a cold email with the matched portfolio links.

3. Example email output:
    ```
    Dear [Client],
    
    I am Syed Sadaqat Yar, a business development executive at AtliQ. AtliQ is an AI & Software Consulting company ...
    ```

## File Structure

```plaintext
.
├── main.py                # Main script for running the workflow
├── my_portfolio.csv       # Portfolio data file
├── requirements.txt       # Dependencies
├── README.md              # Project documentation
└── vectorstore/           # Persistent ChromaDB directory
2