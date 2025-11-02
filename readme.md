# Hugging Face LLM API Demo

This project demonstrates calling Hugging Face LLMs via API using secure keys, handling prompt sets, and tracking usage metrics.

It covers:

- Loading models (e.g., Mistral-7B-Instruct) using **HF API keys** via `os.environ` or `getpass`.
- Fetching datasets from Hugging Face Hub.
- Creating **system prompts** and one-shot examples for controlled outputs.
- Handling **sync vs async calls** for throughput.
- Tracking **input/output tokens**, latency, and status codes.
- Managing **throttling** and **rate limiting**.
- Handling errors due to exceeding **token quotas** (e.g., 402 Payment Required).

## Setup

Install dependencies: tqdm, OS, Inference Client (API server for model call - In my case this was featherless-ai) and HF data sets

### Usage

> Prepare prompt sets (P1, P2, P3).
> Create full prompts including system instructions.
> Call the Hugging Face API and record metrics for each prompt: Input tokens, Output tokens, Latency, Status code

### Key Learnings

System instructions guide model outputs without overloading tokens.

Rate limits prevent excessive API calls; throttling may delay or reject requests.

Exceeding token quotas triggers errors; track usage to estimate cost and avoid 402 errors.

Too much tokens result in quick spike in $$ - Be cautious about System Instructions and Nature of Output

$$ of Output token > $ of Input Token
