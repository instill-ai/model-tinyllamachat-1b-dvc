---
Task: TextGeneration
Tags:
  - TextGenerationChat
  - TinyLlamaChat-1b
---

# Model-TinyLlamaChat-1b-dvc

🔥🔥🔥 Deploy [TinyLlamaChat-1b](https://huggingface.co/TinyLlama/TinyLlama-1.1B-Chat-v1.0) model on [VDP](https://github.com/instill-ai/vdp).

This repository contains the TinyLlamaChat-1b Text Completion Generation Model in the Transformers format, managed using [DVC](https://dvc.org/).

Notes:

- Disk Space Requirements: 2G
- GPU Memory Requirements: 2G

Following is an example of query parameters:

**Create Model**

```json
{
    "id": "tinyllamachat-1b-gpu",
    "description": "TinyLlama-Chat-1b, from TinyLlama, is trained to generate text based on your prompts.",
    "model_definition": "model-definitions/container",
    "visibility": "VISIBILITY_PUBLIC",
    "region": "REGION_GCP_EUROPE_WEST_4",
    "hardware": "GPU",
    "configuration": {
        "task": "TEXT_GENERATION_CHAT"
    }
}
```

**Inference model**

```
{
    "task_inputs": [
        {
            "text_generation_chat": {
                "prompt": "Yo, what's your name?",
                "chat_history": [
                    {
                        "role": "system",
                        "content": [
                            {
                                "type": "text",
                                "text": "Your nams is Tony. A helpful assistant."
                            }
                        ]
                    }
                    ,{
                        "role": "user",
                        "content": [
                            {
                                "type": "text",
                                "text": "I like to call you Toro."
                            }
                        ]
                    },
                    {
                        "role": "ASSISTANT",
                        "content": [
                            {
                                "type": "text",
                                "text": "Ok, My name is Toro. What can I help you?"
                            }
                        ]
                    }
                ],
                // "system_message": "You are not a human.",
                "max_new_tokens": "100",
                "temperature": "0.8",
                "top_k": "10",
                "seed": "42"
                // ,"extra_params": {
                //     "test_param_string": "test_param_string_value",
                //     "test_param_int": 123,
                //     "test_param_float": 0.2,
                //     "test_param_arr": [1, 2, 3],
                //     "test_param_onject": { "some_key": "some_value" }
                // }
            }
        }
    ]
}```
