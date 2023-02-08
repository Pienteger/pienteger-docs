# Introduction

## Overview

The OpenAI API can be applied to virtually any task that involves understanding or generating natural language or code. We offer a spectrum of models with different levels of power suitable for different tasks, as well as the ability to fine-tune your own custom models. These models can be used for everything from content generation to semantic search and classification.

## Key concepts

### Prompts and completions

The completions endpoint is at the center of our API. It provides a simple interface to our models that is extremely flexible and powerful. You input some text as a prompt, and the model will generate a text completion that attempts to match whatever context or pattern you gave it. For example, if you give the API the prompt, “Write a tagline for an ice cream shop”, it will return a completion like “We serve up smiles with every scoop!”

Designing your prompt is essentially how you “program” the model, usually by providing some instructions or a few examples. This is different from most other NLP services which are designed for a single task, such as sentiment classification or named entity recognition. Instead, the completions endpoint can be used for virtually any task including content or code generation, summarization, expansion, conversation, creative writing, style transfer, and more.

### Tokens

Our models understand and process text by breaking it down into tokens. Tokens can be words or just chunks of characters. For example, the word “hamburger” gets broken up into the tokens “ham”, “bur” and “ger”, while a short and common word like “pear” is a single token. Many tokens start with a whitespace, for example “ hello” and “ bye”.

The number of tokens processed in a given API request depends on the length of both your inputs and outputs. As a rough rule of thumb, 1 token is approximately 4 characters or 0.75 words for English text. One limitation to keep in mind is that your text prompt and generated completion combined must be no more than the model's maximum context length (for most models this is 2048 tokens, or about 1500 words). Check out our tokenizer tool to learn more about how text translates to tokens.

### Models

The API is powered by a set of models with different capabilities and price points. Our base GPT-3 models are called Davinci, Curie, Babbage and Ada. Our Codex series is a descendant of GPT-3 that’s been trained on both natural language and code. To learn more, visit our models documentation.

## Next steps

- Keep OpenAi's [usage policies](https://platform.openai.com/docs/usage-policies) in mind as you start building your application.
- Explore our examples for inspiration.
- Jump into one of our guides to start building.
- Check out the [official Documentation](https://platform.openai.com/docs/introduction) for a complete guide to the service.
