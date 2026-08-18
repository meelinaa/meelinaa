# Hi, I'm Melina
.NET Developer | Building backend systems, REST APIs, and full-stack applications

## About Me
I'm a software developer specializing in .NET and ASP.NET Core. I'm completing my apprenticeship as a Software Developer (originally 3 years, completed in 1.5) and will be available for full-time positions starting February 2027.

## How I Work
I write to SOLID principles and keep to Clean Code by default: readable names, small functions, no dead code lying around.

For architecture I pick whatever fits the actual problem. Sometimes that's Hexagonal (Ports & Adapters), keeping the domain isolated from infrastructure. Sometimes a plain layered setup is the honest answer. I try to build what the project needs right now (YAGNI), not what might be useful someday.

Code quality matters just as much to me as working features. A feature built on messy code stands on thin stilts: it works until it doesn't, and then it's expensive to fix. I'd rather ship less and have it hold up.

## Tech Stack
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C Sharp](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Blazor](https://img.shields.io/badge/Blazor-512BD4?style=for-the-badge&logo=blazor&logoColor=white)
![.NET MAUI](https://img.shields.io/badge/.NET_MAUI-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Microsoft SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Entity Framework](https://img.shields.io/badge/Entity_Framework-512BD4?style=for-the-badge&logo=nuget&logoColor=white)
![REST API](https://img.shields.io/badge/REST_API-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

## Featured Projects

### [Hermes](https://github.com/meelinaa/Hermes)
Problem: news is scattered across sources and most people just get whatever an algorithm decides to show them. Hermes lets you set exactly what you want (keywords, categories, countries, languages) and when you want it, then a background worker pulls matching articles from NewsAPI.org and NewsData.io and mails them out as HTML digests.

**Stack:** ASP.NET Core, Blazor WASM, MySQL, Hangfire, Redis, Docker.

Built as Hexagonal Architecture, domain and application logic isolated from infrastructure, with NetArchTest checking those boundaries automatically in CI. JWT auth with refresh token rotation and email verification, Hangfire scheduling backed by MySQL, a live feed explorer where any search can become a subscription with one click, and observability through Serilog, correlation IDs and OpenTelemetry. 810 automated tests across unit, component and integration layers, with Testcontainers spinning up real MySQL and Redis for the integration suite.

### [Elementum](https://github.com/meelinaa/Elementum)
Problem: tracking precious metal prices over time (per metal, per purity, historically) usually means piecing it together from several places by hand. Elementum ingests daily prices automatically and exposes them through an API and a console client, split into a REST API, a background ingestion worker and a CLI, sharing one MySQL database.

**Stack:** ASP.NET Core, MySQL, EF Core, Docker.

Versioned endpoints, flexible queries (latest, by symbol, by date range, aggregated), trading views, health checks, Docker Compose deployment.

### [Warden](https://github.com/meelinaa/Warden)
Problem: when a critical background service crashes, someone has to notice and switch to a backup, often manually and often too late. Warden watches Windows Services, Docker containers and HTTP endpoints and fails over to a backup on its own.

**Stack:** .NET 10, Stateless, Docker.DotNet, Polly, MailKit, Serilog.

A state machine drives Main → Fallback → Recovery and only raises domain events; the worker wires those events to email notifications, so the state machine itself has no idea who gets notified or how. SMTP alerts go through Polly with exponential backoff, dispatched fire-and-forget so a slow retry never blocks the monitoring loop. Docker operations get their own per-call timeout, separate from the host shutdown token, so a Warden restart can't leave a container half-stopped. The REST API is strictly read-only, meant for dashboards.

### [DeskDuck](https://github.com/meelinaa/DeskDuck)
Problem: system monitoring tools are easy to ignore, notifications get lost in the taskbar, and most AI chat assistants send your conversations to someone else's server. DeskDuck is a little mascot that lives on your desktop and shows you important messages via RabbitMQ, so nothing important slips by unnoticed and there's a bit of fun on the desktop while it's at it. It also surfaces CPU/RAM/battery warnings as speech bubbles and gives you a fully local AI chat.

**Stack:** WinUI 3, RabbitMQ, Ollama/OllamaSharp, Docker.

Feature-based layered architecture, UI and Core kept separate, RabbitMQ as the messaging layer between them. The background publishers (system monitor, weather) currently run in the same process for a working demo, but the messaging setup means they could run as separate services just as easily. AI chat runs entirely through a local Ollama model, nothing leaves the machine and there's no API cost. Win32 interop handles the click-through overlay and a global hotkey to recenter the duck on multi-monitor setups.

## Let's Connect
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/melina-kiefer-079370239/)

---
💡 *Available for opportunities in Switzerland, Germany, or remote positions starting February 2027*
