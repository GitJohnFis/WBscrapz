# WBscrapz
scallops of the BIG CORP ads

# Web Crawler CLI

A beginner-friendly Golang command-line tool that crawls websites and generates a report of internal links. Perfect for learning Go, CLI development, and open-source collaboration.

## Project Overview

The Web Crawler CLI is a Go application designed to help developers and website owners analyze and list all internal links on a given website. This tool is ideal for SEO audits, site maintenance, and exploring web architecture.

## Installation

### Prerequisites

- **Go toolchain (version 1.24+)**  
  [Download Go](https://golang.org/doc/install)
- **Boot.dev CLI** (optional for Boot.dev learners)  
  [Boot.dev CLI Guide](https://github.com/Bootdotdev/cli)
- **Bash-like environment**  
  - Native Linux/macOS terminal is recommended
  - For Windows: [WSL 2](https://learn.microsoft.com/en-us/windows/wsl/install) is highly recommended

### Steps

1. **Clone the repository:**
    ```sh
    git clone https://github.com/GitJohnFis/WBscrapz.git
    cd WBscrapz
    ```
2. **Install dependencies:**
    ```sh
    go mod tidy
    ```
3. **Build the CLI tool:**
    ```sh
    go build -o webcrawler
    ```
4. **Verify installation:**
    ```sh
    ./webcrawler --help
    ```

## Usage

To crawl a website and generate an internal links report, run:

```sh
./webcrawler https://example.com
```

This will output a list of all internal links found on the site.

### Additional Options

```sh
./webcrawler --depth 2 https://example.com
```

- `--depth`: Limit the crawl depth (default: unlimited)

For more options, use:

```sh
./webcrawler --help
```

## Contributing

We welcome contributions from beginners and experienced developers!  
See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch
3. Write clear code and comments
4. Format and lint your code
5. Submit a pull request referencing related issues

## License

This project is licensed under the [MIT License](LICENSE).
