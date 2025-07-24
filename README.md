# DocuTalk
 Chat with Multiple PDFs using Langchain and Gemini Pro

# 📄 Chat With Multiple PDFs using Google Gemini & LangChain

This project is an end-to-end application that allows you to chat with multiple PDF documents simultaneously. It leverages the power of Google's Gemini Pro model, LangChain for orchestration, and a Streamlit-based user interface for a seamless experience. 🤖

The application converts the content of uploaded PDF files into vector embeddings, enabling efficient similarity searches to find the most relevant information for answering user queries.


---

## ✨ Features

* **Chat with Multiple PDFs**: Upload and query several PDF documents at once.
* **Generative AI Power**: Utilizes Google Gemini Pro for intelligent and contextual responses.
* **Efficient Data Processing**: Integrates LangChain for robust PDF text extraction and processing.
* **Vector Embeddings**: Converts PDF content into vector embeddings for fast and accurate information retrieval.
* **Local Vector Store**: Uses **FAISS** (Facebook AI Similarity Search) to store vector embeddings locally.
* **User-Friendly UI**: A clean and interactive interface built with **Streamlit**.

---

## 🛠️ Environment Setup

Follow these steps to get your local development environment set up and running.

### Prerequisites

* **Python**: Version `3.9` or higher is recommended for compatibility with Google Gemini Pro.

### 1. Clone the Repository

First, clone this repository to your local machine.

```bash
git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
cd your-repository-name
````

### 2\. Create and Activate a Python Virtual Environment

It's highly recommended to use a virtual environment to manage project dependencies.

  * **Create the environment:**

    ```bash
    python -m venv venv
    ```

  * **Activate the environment:**

      * **Windows:**
        ```bash
        .\venv\Scripts\activate
        ```
      * **macOS / Linux:**
        ```bash
        source venv/bin/activate
        ```

### 3\. Get Your Google API Key

You need a Google API Key to use the Gemini Pro model.

1.  Go to [Google AI Studio](https://makersuite.google.com/app/apikey) to generate your API key.

2.  Click on **"Create API key in a new project"**.

3.  Copy the generated key.

4.  Create a file named `.env` in the root of your project directory and add your API key to it:

    ```env
    GOOGLE_API_KEY="YOUR_API_KEY_HERE"
    ```

    The application uses the `python-dotenv` library to load this key automatically.

### 4\. Install Project Dependencies

Install all the required libraries using the `requirements.txt` file.

  * **Create a `requirements.txt` file with the following content:**
    ```txt
    streamlit
    google-generativeai
    python-dotenv
    langchain
    PyPDF2
    faiss-cpu
    langchain-google-genai
    ```
  * **Install the libraries:**
    ```bash
    pip install -r requirements.txt
    ```
    > **Note:** For larger files or parallel processing, you can use `faiss-gpu` instead of `faiss-cpu`, but this requires a compatible NVIDIA GPU and CUDA setup.

-----

## 🚀 Running the Application

Once your environment is set up, you can start the application.

1.  **Start the Streamlit App:**
    Run the following command in your terminal:

    ```bash
    streamlit run app.py
    ```

2.  **Interact with the Application:**

      * The application will open in a new tab in your web browser.
      * Use the sidebar to upload one or more PDF files.
      * Click the **"Submit & Process"** button. This will process the PDFs, create vector embeddings, and store them locally in a `faiss_index` folder.
      * Once processing is complete, you can type your questions into the chat input box and receive answers sourced directly from your documents.

-----

## 📂 Project Structure

```
.
├── app.py              # Main Streamlit application file
├── requirements.txt    # Project dependencies
├── .env                # Stores the Google API Key (not committed to git)
├── faiss_index/        # Directory for storing local vector embeddings
│   ├── index.faiss
│   └── index.pkl
└── .gitignore          # To ignore venv, .env, __pycache__, and faiss_index/
```

-----

## 🤝 Contributing

Contributions are welcome\! If you have suggestions or want to improve the project, feel free to open a pull request or an issue.

```
