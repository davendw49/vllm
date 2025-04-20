# Test PLM Inference via vLLM

## Quick start

```python
from openai import OpenAI

openai_api_key = "EMPTY"
openai_api_base = "http://localhost:8000/v1"

client = OpenAI(
    api_key=openai_api_key,
    base_url=openai_api_base,
)

chat_response = client.chat.completions.create(
    model="../PLM-Team/PLM-1.8B-Instruct/",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Tell me what is machine learning?"},
    ],
    max_completion_tokens=512,
    temperature=0.6,
)
print("Chat response:", chat_response)
```

- LRC server: /home/c84379517/PLM-Infer/vllm, request via server 12 (IP：89.169.112.39)
- Online docs: http://89.169.112.39:8000/docs#/

## CHANGELOG

- modified `vllm/model_executor/models/registry.py`
- modified `vllm/model_executor/models/plm.py`