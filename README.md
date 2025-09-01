# WeatherDI Demo 🌦️

A simple **ASP.NET Core 9.0** project that demonstrates the use of **Dependency Injection (DI)** in .NET.  
This project shows how to inject different weather services (e.g., `FakeWeatherService` and `RealWeatherService`) into a controller without changing the controller code.

---

## 🚀 Features
- Built with **.NET 9.0**
- Uses **Dependency Injection (DI)** for service management
- Example with `IWeatherService` interface
- Switch easily between multiple implementations (Fake vs. Real service)
- Integrated with **Swagger** for API testing

---

## 📂 Project Structure
WeatherDiDemo/
│── Controllers/
│ └── WeatherController.cs
│── Services/
│ ├── IWeatherService.cs
│ ├── FakeWeatherService.cs
│ └── RealWeatherService.cs
│── Program.cs
│── WeatherDiDemo.csproj

By default, the API will be available at:
HTTP → http://localhost:5077
HTTPS → https://localhost:7123

📖 Swagger UI
To test the APIs via Swagger, open in browser:
https://localhost:7123/swagger

🛠️ Example Usage
GET /weather → returns weather data (from FakeWeather or RealWeather service depending on configuration)
Example JSON response:
{
  "date": "2025-09-01T12:00:00Z",
  "temperatureC": 25,
  "summary": "Sunny"
}


🎯 Learning Points
How Dependency Injection (DI) decouples services from controllers
How to configure DI in Program.cs
How to swap implementations without touching controller logic

📌 Tech Stack
.NET 9.0
ASP.NET Core Web API
Swagger / Swashbuckle

🔄 Dependency Injection Flow
This project demonstrates how controllers depend on abstractions (interfaces) instead of concrete classes.

┌────────────────┐       ┌────────────────────┐       ┌──────────────────────┐
│  Controller    │ ----> │  IWeatherService   │ ----> │  FakeWeatherService   │
│ (WeatherCtrl)  │       │ (Interface)        │       │  or RealWeatherService│
└────────────────┘       └────────────────────┘       └──────────────────────┘
WeatherController depends only on IWeatherService.
At runtime, DI container decides which implementation (FakeWeatherService or RealWeatherService) to inject.
This makes the code flexible, testable, and loosely coupled.
