# Contributing to Web Crawler CLI

Thank you for your interest in improving the Web Crawler CLI project! We welcome contributions from beginners and experienced developers. Please read the following guidelines to help ensure a smooth contribution process.

## Getting Started

1. **Fork the repository** and clone it to your local machine.
2. **Install Go (version 1.24+)**  
   [Go Installation Guide](https://golang.org/doc/install)
3. **(Optional) Install Boot.dev CLI** for learning and exercises:  
   [Boot.dev CLI Guide](https://github.com/Bootdotdev/cli)
4. **Use a bash-like environment:**  
   - Linux/macOS: Use your native terminal.
   - Windows: Highly recommend [WSL 2](https://learn.microsoft.com/en-us/windows/wsl/install).
5. **Install dependencies:**
    ```sh
    go mod tidy
    ```
6. **Run tests:**
    ```sh
    go test ./...
    ```
7. **Build the CLI tool:**
    ```sh
    go build -o webcrawler
    ```
8. **Format your code before committing:**
    ```sh
    go fmt ./...
    ```

## How to Contribute

- **Pick an Issue:**  
  Check open issues, or open a new issue for discussion before starting work.
- **Branch off from main:**  
  Use a descriptive branch name, e.g. `feature/add-output-format`.
- **Make your changes:**  
  Follow code style guidelines and add tests where possible.
- **Commit your work:**  
  Write clear, concise commit messages.
- **Push and create a Pull Request (PR):**  
  - Use the PR template.
  - Reference related issues.
  - Clearly describe your changes.
- **Review and respond:**  
  Address reviewer comments and update your PR as needed.

## Code Style

- Run `go fmt` before committing any code.
- Use `golint` to check for stylistic issues:
    ```sh
    golint ./...
    ```
- Write idiomatic Go code and use standard Go constructs.
- Organize code into logical packages.
- Comment exported functions and types.
- Write table-driven tests for CLI logic and core functions.
- Error messages should be clear and actionable.

## Issue Reporting

- **Search existing issues** before opening a new one.
- **Describe the problem clearly:**  
  Include Go version, OS details, steps to reproduce, expected and actual behavior.
- **Attach logs or screenshots** if helpful.
- **Label your issue** appropriately (`bug`, `feature request`, etc.).

---

Thanks for helping make Web Crawler CLI better!  
The Maintainers
