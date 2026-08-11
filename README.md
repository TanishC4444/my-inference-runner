# my-inference-runner

A GitHub Actions-based worker for running local language-model inference with `llama-cpp-python`.

## Overview

This repository contains the inference-side implementation used to download or reuse a configured GGUF model, execute a prompt, and persist the generated response for workflow consumption.

## Features

- Local LLM inference through `llama-cpp-python`
- GGUF model downloads with local caching
- Configurable prompts and system messages
- Configurable context, temperature, and output length
- GitHub Actions-friendly environment configuration

## Prerequisites

- Python compatible with `llama-cpp-python`
- A supported model/runtime environment
- `MODEL` and `PROMPT` environment variables

## Quick Start

```bash
export MODEL=tinyllama
export PROMPT="Explain recursion in simple terms."
python run_inference.py
```

On Windows PowerShell:

```powershell
$env:MODEL="tinyllama"
$env:PROMPT="Explain recursion in simple terms."
python run_inference.py
```

## Configuration

| Variable | Required | Description |
|---|---|---|
| `MODEL` | Yes | Configured model key |
| `PROMPT` | Yes | User prompt |
| `SYSTEM` | No | System message |
| `MAX_TOKENS` | No | Maximum output tokens |
| `TEMPERATURE` | No | Sampling temperature |
| `N_CTX` | No | Context-window override |

## Output

The worker prints the response and writes it to `output.txt` for downstream automation.

## Status

Experimental inference worker.

## License

No separate license is currently specified in the repository.
