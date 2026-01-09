# OpenRouter Explorer

A web-based tool for exploring and comparing OpenRouter models by throughput, latency, price, context length, and more.

## Quick Start

```bash
cd openrouter-explorer
pip install -r requirements.txt
python server.py
```

Then open http://localhost:8765 in your browser.

## Features

- **Filter by**: throughput, latency, price, context length, modality, provider
- **Sort by**: any metric, ascending or descending
- **Search**: filter models by name or ID
- **Real-time data**: fetches live metrics from OpenRouter API
- **Caching**: 5-minute cache to avoid rate limits

## API Endpoints

- `GET /api/models` - List models with optional filters
  - `q` - Search query
  - `min_throughput` - Minimum throughput (tokens/sec)
  - `max_latency` - Maximum latency (ms)
  - `max_price` - Maximum input price ($/1M tokens)
  - `min_context` - Minimum context length
  - `modality` - Filter by modality (text, image, audio)
  - `provider` - Filter by provider name
  - `sort` - Sort field
  - `desc` - Sort descending (true/false)
  - `limit` - Results per page
  - `offset` - Pagination offset

- `GET /api/stats` - Get aggregate statistics
- `GET /api/refresh` - Force refresh data from API

## Environment Variables

- `PORT` - Server port (default: 8765)
