
# 🌐 LangChain Translation API 💬

This repository provides a simple API server for translating text using LangChain, LCEL (LangChain Expression Language), and the Groq Gemma2-9b-It LLM.  It leverages FastAPI for creating the API and LangServe for easy deployment and interaction.  This guide focuses specifically on Windows environments using Conda.

## ✨ Features ✨

* **Text Translation:** 📝 Translates input text to a specified language.
* **LangChain Integration:** 🔗 Utilizes LangChain's powerful LCEL for defining and executing the translation chain.
* **Groq LLM:** 🤖 Employs the Groq Gemma2-9b-It large language model for high-quality translations.
* **FastAPI Framework:** 🚀 Built with FastAPI for robust and efficient API handling.
* **LangServe Deployment:** ☁️ Integrates with LangServe for streamlined deployment and a user-friendly interface.
* **Environment Variables:** 🔑 Securely manages API keys using `.env` files.

## 🛠️ Technologies Used 🛠️

* **LangChain:**  A framework for building applications with LLMs.  Specifically, we use LCEL for defining the chain.
* **Groq Gemma2-9b-It:** A large language model from Groq used for text translation.
* **FastAPI:** A modern, fast (high-performance) web framework for building APIs with Python.
* **LangServe:** A tool for serving LangChain runnables, making them accessible via API.
* **Uvicorn:** An ASGI server, typically used with FastAPI for running the API.
* **Python:** The programming language used for the project.
* **Conda:**  For environment management.
* **.env:** A format for loading environment variables from a file.

## 🚀 Getting Started (Windows/Conda) 🚀

### ⚙️ Prerequisites ⚙️

* Python 3.9+ (Install via Anaconda/Miniconda)
* A Groq API key (obtainable from the Groq platform)

### 📥 Installation 📥

1. **Fork the repository:**

   Click the "Fork" button in the top right corner of the repository on GitHub ((https://github.com/laavanjan/LLM-application-using-LCEL)).  This creates a copy of the repository in your GitHub account.

2. **Clone your forked repository:**

   ```bash
   git clone [https://github.com/your-github-username/LLM-application-using-LCEL.git](https://www.google.com/search?q=https://github.com/your-github-username/LLM-application-using-LCEL.git) # Replace with your username
   cd LLM-application-using-LCEL
   ```

3. **Create and activate a Conda environment:**

   ```bash
   conda create -n langchain-env python=3.9  # Or your preferred Python version
   conda activate langchain-env
   ```

4. **Install dependencies:**

   ```bash
   conda install -f requirements.txt
   ```

### 🏃 Running the API 🏃

1. **Activate the Conda environment (if you haven't already):**

   ```bash
   conda activate langchain-env
   ```
2. **Create a `.env` file and add your Groq API key:**

    ```bash
    type nul > .env  # Create an empty file (Windows)
    echo GROQ_API_KEY=your_actual_groq_api_key >> .env  # Add API key to .env
    ```


3. **Run the FastAPI application using Uvicorn:**

   ```bash
   uvicorn main:app --reload  # Replace 'main' with the name of your main Python file if it's different
   ```

   This will start the server at `http://127.0.0.1:8000`.

### 💻 Using the API 💻

You can interact with the API through the LangServe interface, which is typically available at `http://127.0.0.1:8000/docs` after running the server.  This provides a user-friendly way to test the API endpoints.

Alternatively, you can use tools like `curl` or Postman to make requests directly.  For example:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"text": "Hello, world!", "language": "French"}' [http://127.0.0.1:8000/chain](http://127.0.0.1:8000/chain)
```

This will send a POST request to the `/chain` endpoint with the text "Hello, world!" and the target language "French".

## 📂 Project Structure 📂

```
LLM-application-using-LCEL/
├── main.py       # Main application file
├── requirements.txt # Project dependencies
└── .env          # Environment variables (API keys)
```

## 🚀 Deployment 🚀

This application can be deployed using various platforms.  LangServe provides documentation and tools to assist with deployment.  Refer to the LangServe documentation for more information.

## 🙌 Contributing 🙌

Contributions are welcome!  Please open an issue or submit a pull request to your forked repository.

## 📝 License 📝

This project is licensed under the GNU General Public License v3.0.  See the [LICENSE](LICENSE) file for details.  (You'll need to create a LICENSE file in your repository)

Key changes:

* **Removed separate ".env" file creation section:** The creation and population of the `.env` file are now done directly within the "Running the API" section. This streamlines the process.
* **Added `echo` command for populating `.env`:** The `echo` command is used to add the `GROQ_API_KEY` to the `.env` file.  This is a more concise way to create and populate the file in Windows.  The user still needs to replace `your_actual_groq_api_key` with their key.

This version is more concise and easier to follow, especially for Windows users.  The API key setup is now integrated directly into the running instructions.
