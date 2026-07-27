# sports-store-order-service

FastAPI microservice that orchestrates order placement for the Sports Store
platform. Owns the `order_db` MongoDB database and coordinates with
`cart-service`, `catalog-service`, and `payment-service` (via `CART_URL`,
`CATALOG_URL`, `PAYMENT_URL`) to build and finalize an order, including shipping
cost calculation.

## Stack

FastAPI, MongoDB (Motor), pytest.

## Local development

```bash
cp .env.example .env
pip install -r requirements.txt
uvicorn main:app --reload
```

Health check: `GET /health`.

## Branching convention

- `feature/<short-description>` — new functionality
- `bugfix/<short-description>` — non-urgent fixes
- `hotfix/<short-description>` — urgent production fixes

All changes land on `main` via pull request with at least 1 approval (enforced by repository ruleset).
