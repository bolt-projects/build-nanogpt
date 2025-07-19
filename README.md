# build nanoGPT (Extended)

This project is an extended and modernized fork of the original [nanoGPT](https://github.com/karpathy/nanoGPT/tree/master) by Andrej Karpathy. It aims to provide a clean, step-by-step, from-scratch reproduction of GPT-2/3-style language models, with improvements and updates for larger tokenizers and sequence lengths.

## Project Overview

- Implements a transformer-based language model, closely following the original nanoGPT educational codebase.
- Now uses the [o200k_base](https://github.com/openai/tiktoken) tokenizer from OpenAI, supporting a vocabulary of ~200K tokens.
- Supports longer context windows (block size 2048) and flexible batch sizes.
- Designed for educational clarity, reproducibility, and easy experimentation.

## Recent Changes

See below for a summary of recent changes and improvements:

```
# Changelog

## [Unreleased]
- Switched tokenizer from 'gpt2' to 'o200k_base' across the project (fineweb.py, train_gpt2.py, hellaswag.py).
- Dynamically set vocab size from the tokenizer instead of hardcoding (affects model config and data processing).
- Changed token storage dtype from uint16 to int32 in fineweb.py to support larger vocab size (~200K tokens).
- Updated all relevant code to use the new vocab size and token dtype.
- Changed block size from 1024 to 2048 in train_gpt2.py (affects model and data loader).
- Changed sequence length T from 1024 to 2048 in train_gpt2.py.
- Changed micro batch size B from 64 to 8 in train_gpt2.py.
- Removed input.txt as part of project cleanup (no longer needed).
```

## Usage

- See `fineweb.py` for dataset download and tokenization.
- See `train_gpt2.py` for model training and configuration.
- See `hellaswag.py` for evaluation on the HellaSwag benchmark.

## Special Thanks

- **Original nanoGPT repo and author:** Andrej Karpathy ([nanoGPT](https://github.com/karpathy/nanoGPT)) for the foundational code and educational resources.
- **OpenAI:** For the [tiktoken](https://github.com/openai/tiktoken) tokenizer and the o200k_base vocabulary.

## License

MIT
