# 🦄 Trade Square API

FastAPI application with PostgreSQL database running in Docker containers.

## 🚀 Quick Start

```bash
# 1. Clone repository
git clone <repository-url>
cd Trade_square

# 2. Setup environment
cp .env.example .env

# 3. Start application
docker-compose up -d

# 4. Verify running
docker-compose ps
```

## 🌐 Access Points

- **API Base**: http://localhost
- **Interactive Docs**: http://localhost/docs
- **Health Check**: http://localhost/health
- **Database Test**: http://localhost/db-test

## 📋 API Endpoints

### 👥 Users
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/users` | Get all users |
| POST | `/users` | Create new user |
| GET | `/users/{id}` | Get user by ID |

### 🛍️ Products
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/products` | Get all products |
| POST | `/products` | Create new product |
| GET | `/products/{id}` | Get product by ID |

### 🔧 System
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | Health check |
| GET | `/db-test` | Database connection test |

## 💡 Usage Examples

### Get Data
```bash
# Get all users
curl http://localhost/users

# Get all products
curl http://localhost/products

# Get specific user
curl http://localhost/users/1
```

### Create Data
```bash
# Create new user
curl -X POST http://localhost/users \
  -H "Content-Type: application/json" \
  -d '{"username": "john", "email": "john@example.com"}'

# Create new product
curl -X POST http://localhost/products \
  -H "Content-Type: application/json" \
  -d '{"name": "iPhone", "price": 999.99, "category": "Electronics"}'
```

## 🐳 Docker Management

```bash
# Start containers
docker-compose up -d

# View logs
docker-compose logs -f

# View specific container logs
docker-compose logs -f trade_square_unicorn

# Stop containers
docker-compose down

# Rebuild and restart
docker-compose up --build -d

# Check container status
docker-compose ps
```

## 🗄️ Database

- **Engine**: PostgreSQL 14
- **Container**: `postgres_db`
- **API Container**: `trade_square_unicorn`
- **Sample Data**: Auto-loaded via `seed.sql`

### Sample Data Included:
- **Users**: alice, bob, charlie
- **Products**: Laptop, Mouse, Keyboard, Monitor, Desk Chair

## 🔒 Security Features

- Environment variables for sensitive data
- Strong password protection
- Health checks for containers
- Git ignore for `.env` files

## 🛠️ Development

```bash
# Edit environment variables
nano .env

# View container logs in real-time
docker-compose logs -f

# Access database directly
docker exec -it postgres_db psql -U dba.admin -d myapp

# Restart specific service
docker-compose restart trade_square_unicorn
```

## 📁 Project Structure

```
Trade_square/
├── app/
│   ├── __init__.py
│   └── main.py          # FastAPI application
├── docker-compose.yml   # Container orchestration
├── Dockerfile          # API container build
├── requirements.txt    # Python dependencies
├── seed.sql           # Database initialization
├── .env              # Environment variables (not in git)
├── .env.example      # Environment template
└── README.md         # This file
```

## 🚨 Troubleshooting

### Container Issues
```bash
# Check container status
docker-compose ps

# View logs
docker-compose logs trade_square_unicorn

# Restart containers
docker-compose restart
```

### Database Issues
```bash
# Test database connection
curl http://localhost/db-test

# Access database directly
docker exec -it postgres_db psql -U dba.admin -d myapp
```

### API Issues
```bash
# Check API health
curl http://localhost/health

# View API documentation
open http://localhost/docs
```

---

**Ready to trade! 🚀**