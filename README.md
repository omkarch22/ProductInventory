# ProductInventory

 ProductInventory System API

A clean, layered ASP.NET Core Web API for managing products and categories using Entity Framework Core with SQL Server. Supports JWT authentication, logging, global error handling, validation, and unit testing.

---

## Features

- Clean Architecture (Domain, Infrastructure, API)
- EF Core with SQL Server
- Repository Pattern
- JWT Authentication
- Global Exception Handling
- Serilog Logging
- Input Validation
- Swagger UI
- Unit Testing with xUnit + Moq

---

## Project Structure

ProductInventorySystem/
├── ProductInventorySystem.API/           # Presentation layer (Web API)
├── ProductInventorySystem.Domain/        # Core business models
├── ProductInventorySystem.Infrastructure/ # EF Core + Repositories
├── ProductInventorySystem.Tests/         # Unit Tests

---

## Getting Started

### 1. *Clone the Repository*
```bash
git clone https://github.com/omkarch22/ProductInventory.git
cd ProductInventory
2. Update SQL Server Connection String

In PrdductInventorySystem.API/appsettings.json:

"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=SampleEF;Trusted_Connection=True;TrustServerCertificate=True;"
}

Change localhost if needed (e.g., localhost\\SQLEXPRESS).

⸻

3. Apply EF Core Migrations

cd ProductInventorySystem.API

# Create the database
dotnet ef database update --project ../ProductInventorySystem.Infrastructure --startup-project .



⸻

4. Run the Application

dotnet run --project ProductInventorySystem.API

Visit: https://localhost:5001/swagger

⸻

Authentication

Login Endpoint

POST /api/auth/login

Sample Credentials

{
  "username": "admin",
  "password": "password"
}

Returns a JWT token to access protected endpoints.

⸻

API Endpoints

Products
	•	GET /api/products
	•	GET /api/products/{id}
	•	POST /api/products
	•	PUT /api/products/{id}
	•	DELETE /api/products/{id}

Supports filtering:

GET /api/products?categoryId=3

Categories
	•	GET /api/categories
	•	GET /api/categories/{id}
	•	POST /api/categories
	•	PUT /api/categories/{id}
	•	DELETE /api/categories/{id}

⸻

Unit Testing

Run tests with:

dotnet test

Tests use xUnit and Moq for mocking repository dependencies.

⸻

Logging

Logs are written to the console using Serilog.

⸻

Requirements
	•	.NET 6 SDK or later
	•	SQL Server
	•	Visual Studio / VS Code

⸻
