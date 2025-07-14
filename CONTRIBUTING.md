# Contributing to Web Crawler CLI

Thank you for your interest in improving the Web Crawler CLI project!  
This Golang command-line tool crawls websites to generate internal links reports, helping optimize sites for Google Search.  
We welcome contributions from beginners and experienced developers alike, especially for documentation, testing, and crawling features.

This guide ensures a smooth contribution process aligned with our learning goals: practicing Go development, HTTP requests, HTML parsing, and unit testing.

## Getting Started

Follow these steps to set up your development environment:

1. **Set up a bash-like environment:**
    - **Linux/macOS:** Use your native terminal (bash, zsh, etc.).
    - **Windows:** Install [WSL 2](https://learn.microsoft.com/en-us/windows/wsl/install) for a Unix-like environment.

2. **Install Go (version 1.24+):**
    ```sh
    go version  # Should output go1.24 or higher
    ```
    - Follow the [Go Installation Guide](https://golang.org/doc/install) if needed.

3. **Install Boot.dev CLI** (optional, for learning exercises):
    ```sh
    boot login  # Log in to Boot.dev
    ```
    - See [Boot.dev CLI Guide](https://github.com/Bootdotdev/cli) for setup.

4. **Fork and clone the repository:**
    ```sh
    git clone https://github.com/yourusername/web-crawler.git
    cd web-crawler
    ```

5. **Install dependencies:**
    ```sh
    go mod tidy
    ```
    - Ensure `golang.org/x/net/html` is included for HTML parsing.

6. **Verify setup:**
    ```sh
    go build -o webcrawler cmd/webcrawler/main.go
    ./webcrawler -url https://example.com
    ```
    - If errors occur, check Go version or WSL 2 setup.

7. *(Optional)* **Install VS Code Go extension:**
    - Install [VS Code](https://code.visualstudio.com/) and the Go extension for enhanced Go support.

8. **Run tests:**
    ```sh
    go test ./...
    boot submit  # Submit to Boot.dev for verification
    ```

## How to Contribute

We value clear, incremental contributions. Follow these steps:

1. **Find or create an issue:**
    - Browse [Issues](https://github.com/yourusername/web-crawler/issues) for tasks labeled `good first issue` or `beginner`.
    - For new ideas, open an issue to discuss before coding.

2. **Create a branch:**
    - Use a descriptive name, e.g., `feature/add-json-output` or `fix/html-parser-bug`.

    ```sh
    git checkout -b feature/add-json-output
    ```

3. **Make changes:**
    - Work in the appropriate package (e.g., `internal/crawler` for crawling logic).
    - Add or update table-driven tests for new functionality.
    - Run `go fmt ./...` and `golint ./...` before committing.

4. **Commit changes:**
    - Use clear commit messages, e.g., `Add JSON output format to links report (#12)`.

    ```sh
    git commit -m "Add JSON output format to links report (#12)"
    ```

5. **Push and create a pull request (PR):**
    ```sh
    git push origin feature/add-json-output
    ```
    - Open a PR on GitHub using the PR template.
    - Reference the issue (e.g., `Fixes #12`).
    - Describe changes clearly and list any new dependencies.

6. **Respond to feedback:**
    - Address reviewer comments promptly.
    - Update your branch and push changes as needed.

## Code Style

To maintain consistency, adhere to these guidelines:

- **Format code:** Run `go fmt ./...` before committing.
- **Lint code:** Use `golint ./...` to catch style issues.
- **Idiomatic Go:**
    - Use explicit error handling (e.g., `if err != nil { return nil, err }`).
    - Name variables and functions clearly (e.g., `ParseLinks` instead of `pl`).
- **HTTP requests:**
    - Use `net/http` for requests and set a timeout (e.g., 10 seconds).
    - Handle rate-limiting to avoid overwhelming servers.
- **HTML parsing:**
    - Use `golang.org/x/net/html` for parsing.
    - Write modular functions (e.g., `ExtractLinks` for link extraction).
- **Code organization:**
    - Place CLI logic in `cmd/webcrawler`.
    - Core crawling logic in `internal/crawler`.
    - Tests in `_test.go` files alongside source files.
- **Comments:**
    - Add godoc comments for exported functions and types (e.g., `// Crawl fetches a website and returns internal links`).
- **Error messages:**
    - Be clear and actionable (e.g., `Failed to fetch URL: timeout exceeded`).

## Testing

Testing is a core learning goal. Follow these practices:

- **Write table-driven tests:**
    - Use Go’s testing package for unit tests.
    - Example for a link parser:
    ```go
    func TestExtractLinks(t *testing.T) {
        tests := []struct {
            name     string
            html     string
            expected []string
        }{
            {"Basic link", `<a href="/about">About</a>`, []string{"/about"}},
            {"No links", `<p>No links here</p>`, []string{}},
        }
        for _, tt := range tests {
            t.Run(tt.name, func(t *testing.T) {
                links := ExtractLinks(tt.html)
                if !reflect.DeepEqual(links, tt.expected) {
                    t.Errorf("got %v, want %v", links, tt.expected)
                }
            })
        }
    }
    ```

- **Run tests locally:**
    ```sh
    go test ./...
    ```

- **Submit to Boot.dev:**
    ```sh
    boot submit
    ```

- **Test coverage:**
    - Aim for high coverage of crawling and parsing functions.
    - Use `go test -cover` to check coverage.

## Issue Reporting

To report bugs or suggest features:

- **Check existing issues** to avoid duplicates.
- **Open a new issue** with:
    - A clear title (e.g., `[BUG] Crawler fails on relative URLs`).
    - Sections: Description, Steps to Reproduce, Expected Behavior, Actual Behavior, Command Used, Output.
    - Example:
        ```
        Command: ./webcrawler -url https://example.com
        Output: panic: nil pointer dereference
        ```
    - Include Go version, OS, and website URL.
- **Use templates:** See `.github/ISSUE_TEMPLATE/bug_report.md` for guidance.
- **Label appropriately:** Use `bug`, `feature request`, or `documentation`.

## Community

We’re excited to support beginners!  
This project is part of a Boot.dev learning exercise, so don’t hesitate to ask questions in issues or PRs.  
Maintainers will provide feedback to help you learn Go, HTTP requests, HTML parsing, and testing.  
Join the Boot.dev community for additional support.

---

Thanks for helping make Web Crawler CLI better!  
**The Maintainers**
