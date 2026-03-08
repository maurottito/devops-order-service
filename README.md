# devops-order-service

Node.js/Express microservice that manages customer orders. Validates products via `devops-product-service` before creating an order.

## Requirements

- Node.js 18+
- PostgreSQL with `ecommerce` schema (see `devops-database`)
- `devops-product-service` running on port 3001

## Setup

```bash
git clone <repo-url>
cd devops-order-service
npm install
```

## Run

```bash
PORT=3002 DB_HOST=localhost DB_NAME=ecommerce DB_USER=postgres DB_PASSWORD=password \
PRODUCT_SERVICE_URL=http://localhost:3001 \
npm start
```

## API Endpoints

| Method  | Path          | Description           |
|---------|---------------|-----------------------|
| GET     | `/health`     | Health check          |
| GET     | `/orders`     | List all orders       |
| POST    | `/orders`     | Create a new order    |
| PATCH   | `/orders/:id` | Update order status   |

## Environment Variables

| Variable              | Default                 |
|-----------------------|-------------------------|
| `PORT`                | `3002`                  |
| `DB_HOST`             | `localhost`             |
| `DB_NAME`             | `ecommerce`             |
| `DB_USER`             | `postgres`              |
| `DB_PASSWORD`         | `password`              |
| `PRODUCT_SERVICE_URL` | `http://localhost:3001` |

|------------------------|-------------------------|-----------------------------------|
| `PORT`                 | `3002`                  | Port the service listens on       |
| `DB_HOST`              | `localhost`             | PostgreSQL host                   |
| `DB_PORT`              | `5432`                  | PostgreSQL port                   |
| `DB_NAME`              | `ecommerce`             | Database name                     |
| `DB_USER`              | `postgres`              | Database user                     |
| `DB_PASSWORD`          | `password`              | Database password                 |
| `PRODUCT_SERVICE_URL`  | `http://localhost:3001` | Base URL for the product service  |

## Available Scripts

| Script      | Description             |
|-------------|-------------------------|
| `npm start` | Start the service       |
| `npm test`  | Run tests with Jest     |

## Folder Structure

```
devops-order-service/
├── src/
│   └── index.js        # Express app and route handlers
├── .env.example        # Environment variable template
├── .gitignore
├── package.json
└── README.md
```
