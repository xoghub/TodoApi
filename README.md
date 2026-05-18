# TodoApi

A simple minimal API for managing To-Do items, built with ASP.NET Core and .NET 10. This project serves as a starting point for building and understanding Minimal APIs in .NET.

## Tech Stack

*   **Framework:** .NET 10.0
*   **Web API:** ASP.NET Core Minimal APIs
*   **Database:** Entity Framework Core (In-Memory Database)
*   **API Documentation:** NSwag (Swagger UI and OpenAPI)

## Prerequisites

*   [.NET 10.0 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or later.

## Installation and Execution

1.  **Clone the repository** (or navigate to the project directory if you already have it):
    ```bash
    cd TodoApi
    ```

2.  **Run the application:**
    ```bash
    dotnet run
    ```

    The application will start, typically on `http://localhost:5000` or `https://localhost:5001` (or another port depending on your `launchSettings.json`).

3.  **Explore the API via Swagger UI:**
    Open your web browser and navigate to:
    ```
    http://localhost:<port>/swagger
    ```
    *(Replace `<port>` with the actual port the app is running on).* From here, you can easily test the endpoints.

## API Endpoints

The API provides the following endpoints for managing to-do items:

| Method | Endpoint | Description | Request Body |
| :--- | :--- | :--- | :--- |
| `GET` | `/todoitems` | Retrieves all to-do items. | None |
| `GET` | `/todoitems/complete` | Retrieves all completed to-do items. | None |
| `GET` | `/todoitems/{id}` | Retrieves a specific to-do item by its ID. | None |
| `POST` | `/todoitems` | Creates a new to-do item. | JSON representation of a `Todo` |
| `PUT` | `/todoitems/{id}` | Updates an existing to-do item. | JSON representation of a `Todo` |
| `DELETE`| `/todoitems/{id}` | Deletes a specific to-do item. | None |

## Data Model

The API manages `Todo` objects with the following structure:

```json
{
  "id": 1,
  "name": "Walk the dog",
  "isComplete": false
}
```

*   **`id`** (Integer): The unique identifier for the to-do item (auto-generated).
*   **`name`** (String): The description or title of the to-do item.
*   **`isComplete`** (Boolean): Indicates whether the to-do item has been finished.

## Database Note

This project is currently configured to use an **In-Memory database** (`Microsoft.EntityFrameworkCore.InMemory`). This means that all data is stored in memory and will be lost when the application is restarted. This setup is ideal for testing and development but should be replaced with a persistent database (like SQL Server, PostgreSQL, SQLite, etc.) for a production environment.
