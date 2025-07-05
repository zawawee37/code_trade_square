# Trade Square API

FastAPI application with PostgreSQL database running in Docker containers.

## Quick Start

1. **Clone and setup**
   ```bash
   cd Trade_square
   cp .env.example .env
   ```

2. **Run the application**
   ```bash
   docker-compose up -d
   ```

3. **Access the API**
   - API: http://localhost
   - API Docs: http://localhost/docs
   - Health Check: http://localhost/health

## API Endpoints

### Users
- `GET /users` - Get all users
- `POST /users` - Create new user
- `GET /users/{id}` - Get user by ID

### Products
- `GET /products` - Get all products
- `POST /products` - Create new product
- `GET /products/{id}` - Get product by ID

### System
- `GET /health` - Health check
- `GET /db-test` - Database connection test

## Example Usage

```bash
# Get all users
curl http://localhost/users

# Create new user
curl -X POST http://localhost/users \
  -H "Content-Type: application/json" \
  -d '{"username": "john", "email": "john@example.com"}'

# Get all products
curl http://localhost/products
```

## Development

```bash
# View logs
docker-compose logs -f

# Stop containers
docker-compose down

# Rebuild and restart
docker-compose up --build -d
```