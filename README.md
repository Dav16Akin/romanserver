# Roman Numeral Server

A simple REST API server written in Go that converts numbers (1-10) to their Roman numeral equivalents.

## Features

- Lightweight HTTP server built with Go's standard library
- Converts integers (1-10) to Roman numerals
- Hot-reloading support with Air for development
- Supervisor configuration for production deployment

## Prerequisites

- Go 1.25.3 or higher
- [Air](https://github.com/air-verse/air) (optional, for hot-reloading during development)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Dav16Akin/romanserver.git
   cd romanserver
   ```

2. Build the server:
   ```bash
   go build -o romanServer/romanServer ./romanServer
   ```

## Usage

### Running the Server

Start the server:
```bash
./romanServer/romanServer
```

The server will start on `http://localhost:8000`.

### API Endpoint

**GET** `/roman_number/{number}`

Converts an integer (1-10) to its Roman numeral equivalent.

#### Examples

| Request | Response |
|---------|----------|
| `GET /roman_number/1` | `"I"` |
| `GET /roman_number/4` | `"IV"` |
| `GET /roman_number/5` | `"V"` |
| `GET /roman_number/9` | `"IX"` |
| `GET /roman_number/10` | `"X"` |

#### Response Codes

| Status Code | Description |
|-------------|-------------|
| 200 | Success - Returns the Roman numeral |
| 400 | Bad Request - Invalid endpoint |
| 404 | Not Found - Number out of range (must be 1-10) |

### Example Request

```bash
curl http://localhost:8000/roman_number/7
```

Response:
```
"VII"
```

## Development

### Hot-Reloading with Air

This project includes an Air configuration for hot-reloading during development.

1. Install Air:
   ```bash
   go install github.com/air-verse/air@latest
   ```

2. Run with hot-reloading:
   ```bash
   air
   ```

### Project Structure

```
romanserver/
├── .air.toml          # Air configuration for hot-reloading
├── go.mod             # Go module definition
├── romanserver.ini    # Supervisor configuration
├── romanNumerals/
│   └── data.go        # Roman numeral mappings
└── romanServer/
    └── main.go        # HTTP server implementation
```

## Roman Numeral Mappings

| Number | Roman Numeral |
|--------|---------------|
| 1 | I |
| 2 | II |
| 3 | III |
| 4 | IV |
| 5 | V |
| 6 | VI |
| 7 | VII |
| 8 | VIII |
| 9 | IX |
| 10 | X |

## License

This project is open source and available under the MIT License.
