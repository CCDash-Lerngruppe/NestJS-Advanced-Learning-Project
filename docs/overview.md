# NestJS Einsteigerkurs

## Zielgruppe & Voraussetzungen

- **Zielgruppe**: Entwickler*innen, die bereits grundlegende Erfahrung mit JavaScript oder TypeScript haben und serverseitige Anwendungen entwickeln möchten.
- **Voraussetzungen**: Grundkenntnisse in Node.js, npm oder yarn, sowie grundlegendes Verständnis von HTTP, REST und asynchroner Programmierung.

---

## Lernziele

- Verständnis der NestJS-Architektur und Philosophie (Module, Controller, Services, Dependency Injection).
- Fähigkeit, einfache RESTful APIs mit NestJS zu erstellen.
- Datenbankanbindung und CRUD-Operationen durchführen.
- Basiskenntnisse in Authentifizierung, Error Handling, Middleware und Pipes.
- Einführung in fortgeschrittene Themen wie GraphQL, WebSockets, Microservices.

---

## Kursübersicht

### Woche 1: Grundlagen & Setup

**Inhalte:**

1. **Was ist NestJS?**  
   - Motivation & Vorteile gegenüber anderen Frameworks (Express, Koa)  
   - NestJS im Ökosystem von Node.js und TypeScript
2. **Installation & Projektstruktur**  
   - Node.js, npm/yarn sicherstellen  
   - Nest CLI installieren: `npm i -g @nestjs/cli`  
   - Erstes Projekt erzeugen mit `nest new project-name`
3. **Anatomie eines NestJS-Projekts**  
   - Ordnerstruktur (src, main.ts, app.module.ts)  
   - Module, Controller, Services erklärt
4. **Erster Controller & Service**  
   - Aufbau einer einfachen „Hello World“-Route  
   - Verständnis von Dekoratoren (`@Controller`, `@Get`, `@Injectable`)

**Übungen:**

- Erstelle ein neues NestJS-Projekt.
- Implementiere einen einfachen Controller mit einer GET-Route, die „Hello World“ zurückgibt.
- Erstelle einen Service, der eine Nachricht zurückgibt, und binde ihn im Controller ein.

**Ressourcen:**

- [Offizielle NestJS-Dokumentation – Fundamentals](https://docs.nestjs.com/)
- [NestJS GitHub-Repository](https://github.com/nestjs/nest)

---

### Woche 2: Core-Konzepte Vertiefen

**Inhalte:**

1. **Dependency Injection (DI)**  
   - Wie funktioniert DI in NestJS?  
   - Provider und `@Injectable()` verstehen
2. **Module-System**  
   - Organisation von Features in Module  
   - Import-/Export-Mechanismen von Modulen
3. **Routing & Request Handling**  
   - HTTP-Methoden (GET, POST, PUT, DELETE)  
   - Route-Parameter, Query-Parameter und Body-Parsing
4. **Middleware, Guards & Interceptors (Grundlagen)**  
   - Middleware: Vorverarbeitung von Requests  
   - Guards: Auth-/Access-Kontrolle  
   - Interceptors: Transformierung von Responses

**Übungen:**

- Erstelle ein eigenes Modul, z. B. ein `UsersModule`.
- Erstelle einen `UsersController` mit einer einfachen CRUD-Logik (Mock-Daten).
- Implementiere eine einfache Middleware, die jede Anfrage in der Konsole loggt.

**Ressourcen:**

- [NestJS – Modules](https://docs.nestjs.com/modules)
- [NestJS – Controllers](https://docs.nestjs.com/controllers)
- [NestJS – Providers](https://docs.nestjs.com/providers)

---

### Woche 3: Datenbankschicht & ORM-Integration

**Inhalte:**

1. **Einführung in Datenbanken & ORMs**  
   - Wahl der Datenbank (PostgreSQL, MySQL, MongoDB etc.)  
   - Einsatz von ORMs wie TypeORM oder Prisma
2. **Anbindung einer Datenbank mit TypeORM**  
   - Installation und Konfiguration von TypeORM  
   - Erstellung von Entities  
   - Migrationen und Connection Handling
3. **Repository & Service Layer**  
   - Umgang mit Repositorys (CRUD-Operationen)  
   - Fehlerbehandlung bei DB-Operationen

**Übungen:**

- Binde eine PostgreSQL-Datenbank an.
- Erstelle eine `User`-Entity mit Feldern wie `id`, `name`, `email`.
- Implementiere CRUD-Endpunkte für Benutzer (Create, Read, Update, Delete) mit Anbindung an die Datenbank.

**Ressourcen:**

- [TypeORM Offizielle Dokumentation](https://typeorm.io/#/)
- [NestJS – Database](https://docs.nestjs.com/techniques/database)

---

### Woche 4: Validierung, Fehlerbehandlung & Security

**Inhalte:**

1. **Pipes & Validierung**  
   - Verwendung von `class-validator` und `class-transformer`  
   - Globale ValidationPipes für automatisches Request-Body-Checking
2. **Exception Handling & Filters**  
   - Verwendung von `HttpException`  
   - Custom Exception Filters für individuelle Fehlerausgaben
3. **Authentifizierung & Autorisierung**  
   - JWT-basierte Authentifizierung  
   - Guards für Role-based Access Control (RBAC)
4. **Sicherheit & Best Practices**  
   - CORS, CSRF, Rate-Limiting und helmet.js  
   - Vermeiden von Sicherheitslücken (z. B. SQL-Injection) durch ORM und Validierung

**Übungen:**

- Implementiere eine globale ValidationPipe.
- Erstelle ein Auth-Modul, das Benutzer registriert und JWTs ausgibt.
- Schütze bestimmte Routen mit einem Auth-Guard.

**Ressourcen:**

- [NestJS – Validation](https://docs.nestjs.com/techniques/validation)
- [NestJS – Exception Filters](https://docs.nestjs.com/exception-filters)
- [NestJS – Guards](https://docs.nestjs.com/guards)

---

### Woche 5: Erweiterte Themen (GraphQL, WebSockets, Task Scheduling)

**Inhalte:**

1. **GraphQL mit NestJS**  
   - Einführung in GraphQL-Resolver  
   - Schema-Definition & SDL  
   - Queries, Mutations und Subscriptions
2. **Echtzeitfunktionen mit WebSockets**  
   - Socket.io oder native WebSocket-Adapter  
   - Broadcasten von Nachrichten an Clients
3. **Cron Jobs & Scheduling**  
   - Verwendung von Nest Schedule oder `@nestjs/schedule`  
   - Regelmäßige Tasks einrichten (z. B. Cleanup, Reports)
4. **Internationalisierung (i18n)**  
   - Integration von Übersetzungen und Lokalisierung

**Übungen:**

- Füge GraphQL in das Projekt ein: Erstelle einen Resolver für `Users`.
- Implementiere eine simple WebSocket-Verbindung, um Nachrichten in Echtzeit auszugeben.
- Plane einen Cron Job, der täglich einen Report in der Konsole ausgibt.

**Ressourcen:**

- [NestJS – GraphQL](https://docs.nestjs.com/graphql/quick-start)
- [NestJS – WebSockets](https://docs.nestjs.com/websockets/gateways)
- [NestJS – Schedule](https://docs.nestjs.com/techniques/task-scheduling)

---

### Woche 6: Mikroservices & Skalierung

**Inhalte:**

1. **Mikroservice-Architektur verstehen**  
   - Vorteile und Herausforderungen von verteilten Systemen
2. **NestJS-Mikroservices**  
   - Kommunikation über Message Broker (z. B. RabbitMQ, Kafka)  
   - Erstellung von Clients und Patterns (Request/Response, Event-basiert)
3. **Performance & Skalierbarkeit**  
   - Caching (Redis-Integration)  
   - Horizontal Scaling und Load Balancing
4. **Testing & Best Practices**  
   - Unit-Tests für Controller und Services  
   - Integrationstests mit Datenbank  
   - CI/CD-Pipelines für NestJS-Projekte

**Übungen:**

- Implementiere einen einfachen Mikroservice, der Nachrichten von einem Message Broker empfängt.
- Schreibe Unit-Tests für einen Service und Integrationstests für einen Endpunkt.
- Setze Caching ein, um häufige Datenabfragen zu beschleunigen.

**Ressourcen:**

- [NestJS – Microservices](https://docs.nestjs.com/microservices/basics)
- [NestJS – Testing](https://docs.nestjs.com/fundamentals/testing)
- [NestJS – Caching](https://docs.nestjs.com/techniques/caching)

---

### Abschluss: Projektarbeit & Deployment

**Abschlussprojekt:**

- Erstelle eine vollständige Anwendung (z. B. eine kleine Social-Media-API oder ein Blog-System) mit:
  - Authentifizierung und Rollen
  - Datenbankanbindung mit TypeORM
  - Input-Validierung, Exception-Handling
  - Optional: WebSockets oder GraphQL
- Schreibe Tests für kritische Logik.
- Implementiere CI/CD-Workflow (z. B. mit GitHub Actions).

**Deployment:**

- Grundlagen des Deployments von NestJS-Anwendungen auf AWS, Azure oder Heroku.
- Docker-Container für Produktion bauen.
- Logging und Monitoring (z. B. via Winston oder Loggly).

---

## Weiterführende Schritte & Ressourcen

- **Erweiterte Konzepte**: Domain-Driven Design, CQRS-Pattern, Event Sourcing.
- **Community & Support**:  
  - Offizieller NestJS Discord-Server  
  - StackOverflow Fragen  
  - YouTube-Tutorials und Vorträge
- **Best Practices**:  
  - Code-Organisation, Linting, und Coding-Standards  
  - Secrets Management (z. B. mit Vault, AWS Secret Manager)

---

## Fazit

Dieser Kurs bietet eine solide Grundlage für den Einstieg in NestJS. Angefangen bei den grundlegenden Konzepten über Datenbankanbindung, Authentifizierung, bis hin zu komplexeren Themen wie GraphQL und Mikroservices, erhältst du ein tiefgreifendes Verständnis für den Aufbau moderner, skalierbarer Backend-Systeme mit NestJS. Die abschließende Projektarbeit und das Deployment runden das Gesamtbild ab und bereiten dich auf praktische Anwendungen im Berufsalltag vor.
