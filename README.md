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


