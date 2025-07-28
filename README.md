# App

## Getting Started

### Python Environment (IMPORTANT)

This course repo contains everything you need to install an exact duplicate Python environment as used during the course creation.

#### Installing Python Venvs

The Python packages are managed using the [uv](https://github.com/astral-sh/uv) package manager, and so we must install `uv` as a prerequisite for the course. We do so by following the [installation guide](https://docs.astral.sh/uv/#getting-started). For Mac users enter the following in your terminal:

```
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Once `uv` is installed and available in your terminal you can navigate to the course root directory and execute:

```
uv python install 3.12.7
uv venv --python 3.12.7
source .venv/bin/activate
```

Then run this command (you must have `pyproject.toml` dependency file):
```
uv sync
```

>❗️ You may need to restart the terminal if the `uv` command is not recognized by your terminal.


### Export the environment variables 

The application requires several API keys to function properly. You'll need to set up the following environment variables:

1. **Copy the example environment file:**

   ```bash
   cp env.example .env
   ```

2. **Edit the `.env` file and add your API keys:**

   ```bash
   OPENAI_API_KEY=your_openai_api_key_here
   LANGCHAIN_API_KEY=your_langchain_api_key_here
   SERPAPI_API_KEY=your_serpapi_api_key_here
   ```

3. **For Mac/Linux users, you can also use the provided `mac.env` file:**

   ```bash
   cp mac.env .env
   # Then edit .env to add your actual API keys
   ```

4. **Load the environment variables:**
   - If using a `.env` file, the application will automatically load it
   - Alternatively, you can export them directly in your terminal:

     ```bash
     export OPENAI_API_KEY=your_openai_api_key_here
     export LANGCHAIN_API_KEY=your_langchain_api_key_here
     export SERPAPI_API_KEY=your_serpapi_api_key_here
     ```

#### Where to get the API keys

- **OpenAI API Key**: Sign up at [OpenAI Platform](https://platform.openai.com/) and create an API key
- **LangChain API Key**: Get your key from [LangSmith](https://smith.langchain.com/) (optional, for tracing and monitoring)
- **SerpAPI Key**: Register at [SerpAPI](https://serpapi.com/) to get your API key for web search functionality

> ⚠️ **Important**: Never commit your actual API keys to version control. The `.env` file should be added to your `.gitignore` file.


## Run the API

- `cd` into the `/api` directory
- execute `uv run uvicorn main:app --reload` to start the API
- you can find the API docs at `http://localhost:8000/docs`
- you can test the streaming by running the `streaming-test.ipynb` notebook

## Run the App

- `cd` into the `/app` directory
- execute `npm install` to install the dependencies
- if you see security vulnerabilities after installation, run `npm audit fix` to address them
- execute `npm run dev` to start the app
- you can find the app at `http://localhost:3000`
