# Api References

You can interact with the API through HTTP requests from any language. Keep in mind that, using OpenAi's SDK is not supported by us.

## Authentication

We use API keys for authentication. Visit your [API Keys](https://portal.pienteger.com/account/api-keys) page to retrieve the API key you'll use in your requests.

Remember that your API key is a secret! Do not share it with others or expose it in any client-side code (browsers, apps). Production requests must be routed through your own backend server where your API key can be securely loaded from an environment variable or key management service.

All API requests should include your API key in an X-Api-Key HTTP header as follows:

```text
X-Api-Key: YOUR_API_KEY
```

## Making requests

You can paste the command below into your terminal to run your first API request. Make sure to replace YOUR_API_KEY with your secret API key.

```bash
curl https://api.pienteger.com/oaiv1/completions \
-H "X-Api-Key: YOUR_API_KEY" \
-d '{"model": "text-davinci-003", "prompt": "Say this is a test", "temperature": 0, "max_tokens": 7}'
```

This request queries the Davinci model to complete the text starting with a prompt of "Say this is a test". The max_tokens parameter sets an upper bound on how many [tokens](https://platform.openai.com/tokenizer) the API will return. You should get a response back that resembles the following:

```json
{
    "id": "cmpl-GERzeJQ4lvqPk8SkZu4XMIuR",
    "object": "text_completion",
    "created": 1586839808,
    "model": "text-davinci:003",
    "choices": [
        {
            "text": "\n\nThis is indeed a test",
            "index": 0,
            "logprobs": null,
            "finish_reason": "length"
        }
    ],
    "usage": {
        "prompt_tokens": 5,
        "completion_tokens": 7,
        "total_tokens": 12
    }
}
```

Now you've generated your first completion. If you concatenate the prompt and the completion text (which the API will do for you if you set the echo parameter to true), the resulting text is "Say this is a test. This is indeed a test." You can also set the stream parameter to true for the API to stream back text (as [data-only server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events#Event_stream_format)).

## Models

List and describe the various models available in the API. You can refer to the Models documentation to understand what models are available and the differences between them.

### List models

```text
GET https://api.pienteger.com/oaiv1/getmodels
```

Lists the currently available models, and provides basic information about each one such as the owner and availability.

### Example request

```bash
curl https://api.pienteger.com/oaiv1/getmodels \
  -H 'X-Api-Key: YOUR_API_KEY'
```

### Example response

```json
{
  "data": [
    {
      "id": "model-id-0",
      "object": "model",
      "owned_by": "organization-owner",
      "permission": [...]
    },
    {
      "id": "model-id-1",
      "object": "model",
      "owned_by": "organization-owner",
      "permission": [...]
    },
    {
      "id": "model-id-2",
      "object": "model",
      "owned_by": "openai",
      "permission": [...]
    },
  ],
  "object": "list"
}
```
