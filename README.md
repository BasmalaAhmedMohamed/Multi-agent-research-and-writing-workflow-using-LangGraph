# Research and Writing Agents

This project builds a multi-agent research and writing workflow in a Jupyter notebook using LangGraph. The workflow can gather source material from Wikipedia, generate a draft, review it against the task, and send it back for one revision when needed.

## Project file

- `project.ipynb` — notebook containing the researcher, writer, and reviewer graphs, their visualizations, and a combined orchestration workflow.

## Workflow

1. **Researcher** — searches Wikipedia for relevant source material.
2. **Writer** — drafts a response using the task and research.
3. **Reviewer** — returns actionable feedback and an approval decision.
4. **Orchestrator** — connects the agents and allows a second writing attempt if the first draft is not approved.

The notebook includes standalone examples for each agent as well as a complete coffee-shop slogan workflow.

## Requirements

Use Python with Jupyter Notebook or JupyterLab. The notebook imports these packages:

- `langgraph`
- `langchain-core`
- `langchain-openai`
- `langchain-community`
- `langchain-text-splitters`
- `wikipedia-api`
- `faiss-cpu`
- `pydantic`
- `python-dotenv`
- `ipython`

Install them in your environment, for example:

```bash
pip install langgraph langchain-core langchain-openai langchain-community langchain-text-splitters wikipedia-api faiss-cpu pydantic python-dotenv ipython notebook
```

## Configuration

The notebook loads environment variables with `python-dotenv`. Create a `.env` file in the project directory and set:

```dotenv
OPENAI_API_KEY=your-api-key
openai_model=your-chat-model
openai_embedding_model=your-embedding-model
```


## Run

1. Install the requirements and configure the environment variables above.
2. Start Jupyter from the project directory:

   ```bash
   jupyter notebook
   ```

3. Open `project.ipynb` and run the cells from top to bottom. The notebook makes requests to OpenAI and Wikipedia, so network access and a valid API key are required.

The model names are supplied through environment variables so they can be changed without editing the notebook.
