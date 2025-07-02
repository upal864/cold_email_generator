# Cold Email Generator

## 📧 Overview

The Cold Email Generator is a Streamlit-based web application that helps business development professionals create personalized cold emails for potential clients. The application uses AI to analyze job postings, match them with relevant portfolio items, and generate tailored cold emails that showcase your company's capabilities.

## 🚀 Features

- **Job Description Analysis**: Extracts key information from job postings including role, experience requirements, skills, and description
- **Portfolio Matching**: Automatically matches job requirements with relevant portfolio items from your company
- **Personalized Email Generation**: Creates customized cold emails that highlight your company's relevant experience
- **Web Scraping**: Extracts job information directly from URLs
- **Vector Database**: Uses ChromaDB for efficient semantic matching of skills to portfolio items

## 🛠️ Technology Stack

- **Frontend**: Streamlit
- **AI/ML**: LangChain, Groq LLM (llama-3.3-70b-versatile)
- **Vector Database**: ChromaDB
- **Data Processing**: Pandas
- **Web Scraping**: LangChain WebBaseLoader

## 📋 Prerequisites

- Python 3.x
- Groq API Key

## 🔧 Installation

1. Clone the repository

```bash
git clone https://github.com/upal864/cold_email_generator.git
cd cold_email
```

2. Create and activate a virtual environment (optional but recommended)

```bash
python -m venv venv
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
```

3. Install the required dependencies

```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the app directory with your Groq API key

```
GROQ_API_KEY=your_groq_api_key_here
```

## 📊 Project Structure

```
├── app/
│   ├── .env                  # Environment variables (API keys)
│   ├── chains.py             # LangChain implementation for AI tasks
│   ├── main.py               # Streamlit application entry point
│   ├── portfolio.py          # Portfolio management and matching
│   ├── utils.py              # Utility functions for text processing
│   └── resource/
│       └── my_portfolio.csv  # Portfolio data with tech stacks and links
├── vectorstore/              # ChromaDB persistent storage
├── requirements.txt          # Project dependencies
└── README.md                 # Project documentation
```

## 🚀 Usage

1. Start the Streamlit application

```bash
cd app
streamlit run main.py
```

2. Open your web browser and navigate to the URL displayed in the terminal (typically http://localhost:8501)

3. Enter a job posting URL in the input field and click "Submit"

4. The application will analyze the job posting, match it with relevant portfolio items, and generate a personalized cold email

## 📝 Customizing Your Portfolio

The application uses a CSV file located at `app/resource/my_portfolio.csv` to store your portfolio information. You can customize this file with your own tech stacks and portfolio links.

The CSV file has two columns:
- **Techstack**: Comma-separated list of technologies (e.g., "React, Node.js, MongoDB")
- **Links**: URL to the portfolio item showcasing those technologies

## 🧠 How It Works

1. **Web Scraping**: The application scrapes job information from the provided URL
2. **Text Cleaning**: Removes HTML tags, URLs, and special characters from the scraped text
3. **Job Extraction**: Uses LLM to extract structured job information (role, experience, skills, description)
4. **Portfolio Matching**: Matches job skills with relevant portfolio items using vector similarity search
5. **Email Generation**: Creates a personalized cold email highlighting your company's capabilities and relevant portfolio items

## 🔒 Security Notes

- Store your API keys securely in the `.env` file and never commit them to version control
- The application is designed for local use and may require additional security measures for production deployment

## 📄 License

[MIT License](LICENSE)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
