# 🤖 AI Code Reviewer

A GitHub Action that automatically reviews pull requests with LLMs — now powered by **Google Gemini 2.5**.

> **Attribution:** This project is based on [tusgino/llm-code-reviewer](https://github.com/tusgino/llm-code-reviewer) (MIT License). I modernized the Gemini integration and defaults.

## What it does

- 👀 Reviews every PR diff automatically
- 💬 Posts line-level review comments with bug, security, and performance findings
- 🔌 Supports Gemini, OpenAI, and Anthropic backends

## What changed from the original

- Migrated the Gemini provider from the **deprecated** `google-generativeai` SDK (gRPC) to the current `google-genai` HTTP client
- Updated the default model from the retired `gemini-1.5-flash-002` to `gemini-2.5-flash`
- Added `no_proxy` sanitization for sandboxed/proxied environments
- Cleaned up `requirements.txt`

## Usage

```yaml
- uses: HuzaifaAqeel/AI-Code-Reviewer@v1
  with:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    GEMINI_API_KEY: ${{ secrets.GEMINI_API_KEY }}
    GEMINI_MODEL: 'gemini-2.5-flash'
```

## License

MIT — see [LICENSE](LICENSE) (original license by tusgino, preserved).
