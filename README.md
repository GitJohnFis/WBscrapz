# WBscrapz
scallops of the BIG CORP ads

# Decos Chatbot

A beginner-friendly, Golang-based chatbot project that provides a REST API for managing decoration-themed items. Built with [Gin-gonic](https://github.com/gin-gonic/gin), Decos helps users explore, filter, and calculate decoration options through a simple API.

## Project Overview

Decos is designed to showcase how to build a RESTful chatbot backend in Go. The API lets users:
- List and filter decoration items
- Calculate decoration costs
- Interact with chatbot endpoints

The project is ideal for learning Go web development, REST API design, and open-source collaboration.

## Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/GitJohnFis/WBscrapz.git
    cd WBscrapz
    ```
2. **Install Go (>=1.20):**  
   [Install Go](https://golang.org/doc/install)
3. **Install dependencies:**
    ```sh
    go mod tidy
    ```
4. **Run the server:**
    ```sh
    go run main.go
    ```

## Usage

Once the server is running on `localhost:8080`, you can interact with the API using curl or any HTTP client.

### Example: List Decorations

```sh
curl -X GET "http://localhost:8080/decorations"
```

### Example: Filter Decorations by Price

```sh
curl -X GET "http://localhost:8080/decorations?min_price=10&max_price=50"
```

### Example: Calculate Decoration Cost

```sh
curl -X POST "http://localhost:8080/calculate" \
  -H "Content-Type: application/json" \
  -d '{"decoration_id":1,"quantity":3}'
```

## API Endpoints

| Endpoint                | Method | Description                               |
|-------------------------|--------|-------------------------------------------|
| `/decorations`          | GET    | List all decoration items                 |
| `/decorations`          | GET    | Filter decorations by price, category, etc|
| `/decorations/:id`      | GET    | Get details for a specific decoration     |
| `/calculate`            | POST   | Calculate cost for given decorations      |

See [OpenAPI docs](./docs/openapi.yaml) for full details.

## Contributing

We welcome contributions from beginners and experienced developers!  
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

- Fork the repo and create your branch
- Write clear code and comments
- Format code with `go fmt` and lint with `golint`
- Submit a pull request referencing relevant issues

## License

This project is licensed under the [MIT License](LICENSE).
