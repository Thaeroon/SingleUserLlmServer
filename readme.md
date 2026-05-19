# Prerequisites

## Download the model
3 dots on the right then choose your poison.
```
https://huggingface.co/UnstableLlama/Qwen3.6-27B-exl3-4.15bpw
```
put it in `models\Qwen3.6-27B-exl3-4.15bpw`

## Web Search (MCP)

The `mcp-searxng` service is defined in `docker-compose.yml`. Configure your MCP client (Cline) with:

```json
{
  "mcpServers": {
    "searxng": {
      "command": "docker",
      "args": [
        "compose",
        "-f",
        "<PATH_TO_THE_PROJECT>\\models\\qwen3.6-27B-exl3\\docker-compose.yml",
        "run",
        "--rm",
        "mcp-searxng"
      ],
      "autoApprove": [
        "searxng_web_search",
        "web_url_read"
      ]
    }
  }
}
```

## Start it all

```bash
docker compose up -d
```

## note
When modifying the config, to make sure all your changes are taken into account, use:
```bash
docker compose up -d --build --force-recreate
```