# Lab 5 – Postman and APIs

A Flask REST API that adds, reads, updates and deletes users in a SQLite database, tested with Postman.

**Author:** Tatiana Nohra – EECE 435L

## How to run

```
pip install flask flask-cors
python app.py
```

The server runs at `http://localhost:5000`. On first run it creates `database.db` with a `users` table.

## API endpoints

| # | Method | Endpoint | Description |
|---|--------|----------|-------------|
| 1 | GET | `/api/users` | Get the list of all users |
| 2 | GET | `/api/users/<user_id>` | Get a single user by ID |
| 3 | POST | `/api/users/add` | Create a new user (JSON body) |
| 4 | PUT | `/api/users/update` | Update a user (JSON body, includes `user_id`) |
| 5 | DELETE | `/api/users/delete/<user_id>` | Delete a user |

Example body for POST:

```json
{
    "name": "John Doe",
    "email": "jondoe@gamil.com",
    "phone": "067765434567",
    "address": "John Doe Street, Innsbruck",
    "country": "Austria"
}
```

## Postman

- `Flask user app.postman_collection.json` – the **Flask user app** collection with one request per endpoint, each with a saved example.
- `Flask local.postman_environment.json` – the **Flask local** environment, which stores the URL as `base_url` (`http://localhost:5000`). All requests use `{{base_url}}`.

To use: in Postman, **Import** both files, then select **Flask local** in the environment dropdown.

## Screenshots

The `screenshots/` folder shows each Postman request and response, the environment and the collection.

## Git workflow

1. Database code committed on `main`.
2. REST API built on the `rest-api` branch, tested in the browser, then merged into `main`.
3. Postman collection, environment and screenshots added on `main`.
