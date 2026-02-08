# moviebox

A JSON API for retrieving and managing movie information, built in Go. Inspired by the Open Movie Database API.

## Endpoints

| Method | Route | Description |
|--------|-------|-------------|
| `GET` | `/v1/health` | Health check |
| `GET` | `/v1/movies/:id` | Get a movie |
| `POST` | `/v1/movies` | Create a movie |

## Example

```bash
# Create a movie
curl -X POST localhost:4000/v1/movies \
  -H "Content-Type: application/json" \
  -d '{"title":"Casablanca","year":1942,"runtime":"102 mins","genres":["drama","romance","war"]}'

# Get a movie
curl localhost:4000/v1/movies/1
```

## Running

```bash
go run ./cmd/api
```

Listens on `:4000` by default. Override with `-port` and `-env` flags.

## Built With

- Go standard library (`net/http`, `encoding/json`)
- [httprouter](https://github.com/julianbrunner/httprouter) for routing
- Custom input validation and JSON error handling
