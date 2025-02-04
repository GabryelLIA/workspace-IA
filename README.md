# AI Tools Docker Environment

This Docker Compose setup provides an environment with the following tools:

- **n8n**: Workflow automation platform (available at http://localhost:5679)
- **Ollama**: AI model serving platform (available at http://localhost:11435)
- **OpenWebUI**: User interface for LLMs (available at http://localhost:3001)
- **Langfuse**: LLM observability platform (available at http://localhost:3002)

## Getting Started

1. Make sure you have Docker and Docker Compose installed on your system.
2. Start the services:
   ```bash
   docker compose up -d
   ```

## Service Access

- n8n: http://localhost:5679
- Ollama API: http://localhost:11435
- OpenWebUI: http://localhost:3001
- Langfuse: http://localhost:3002

## Data Persistence

All data is persisted using Docker volumes:
- `n8n_data`: Stores n8n workflows and data
- `ollama_data`: Stores Ollama models and configurations
- `langfuse_db_data`: Stores Langfuse observability data

## Langfuse Setup

1. Start the services and access Langfuse at http://localhost:3002
2. Create your first account (this will be the admin account)
3. Create a new project in Langfuse
4. Get your API keys from the project settings
5. Update the `.env` file with your Langfuse API keys:
   ```env
   LANGFUSE_PUBLIC_KEY=pk-lf-your-public-key
   LANGFUSE_SECRET_KEY=sk-lf-your-secret-key
   ```
6. Restart the services to apply the new API keys

## Stopping the Services

To stop all services:
```bash
docker compose down
```

To stop and remove all data (volumes):
```bash
docker compose down -v
```
