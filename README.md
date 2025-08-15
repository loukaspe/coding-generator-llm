# Coding Generator LLM

An AI-powered code generation tool written in **Go** that uses **OpenAI's API** to create complete, multi-language projects from natural language prompts.

This project is based on the Udemy course:  
[**AI for Everyone: Build a Complete Code Writing Agent with Go**](https://www.udemy.com/course/ai-for-everyone-build-a-complete-code-writing-agent-with-go/)  
and adapted from the original GitHub repository:  
[https://github.com/joefazee/ai-agent-maker](https://github.com/joefazee/ai-agent-maker/tree/main)

---

## Features

- **Multi-language support** — Generate code in Go, Python, JavaScript, and Java
- **Concurrent file processing** — Uses Go's goroutines for faster generation
- **Flexible templates** — Supports multiple project types and frameworks
- **Robust error handling** — Built for production-level AI applications
- **Configurable** — Choose language, template, AI model, and more
- **Testable** — Mock OpenAI responses for predictable unit tests

---

## Requirements

- Go 1.21+
- An OpenAI API key
- Internet connection (for API calls)

---

## Installation

```bash
git clone https://github.com/loukaspe/coding-generator-llm.git
cd coding-generator-llm
go mod tidy
```

---

## Usage

Basic run example:

```bash
go run ./cmd/maker/main.go   -template python-django   -language python   -model o3-mini   -output-dir ./book-keeper   "create a simple book keeping application"
```

---

## Command-Line Options

| Flag              | Default                    | Description |
|-------------------|----------------------------|-------------|
| `-openai-key`     | `""`                        | OpenAI API key |
| `-output-dir`     | `./output`                  | Output directory for generated files |
| `-base-package`   | `github.com/user/app`       | Base package name for generated Go code |
| `-worker-count`   | `4`                         | Number of concurrent workers for file generation |
| `-template`       | `default`                   | Project template to use |
| `-language`       | `go`                        | Programming language to use |
| `-model`          | `gpt-4o-mini`               | OpenAI model to use |
| `-timeout`        | `120`                       | Timeout (in seconds) for OpenAI API calls |
| `-list-templates` | `false`                     | List available templates and exit |
| `-list-languages` | `false`                     | List supported programming languages and exit |

---

## Example

Generate a Go web service using the default template:

```bash
go run ./cmd/maker/main.go   -template default   -language go   -model gpt-4o-mini   -output-dir ./web-service   "create a REST API for managing tasks"
```

---

## License

This project is provided for educational purposes only as part of the Udemy course mentioned above. Please review the original repository’s license before commercial use.
