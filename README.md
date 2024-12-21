# NestJS Advanced Learning Project (Erweiterte Lernprojekt für NestJS)

Willkommen beim **NestJS Advanced Learning Project**! Dieses Repository bietet eine umfassende Anleitung und praktische Übungen, um fortgeschrittene Konzepte in NestJS zu meistern, darunter Domain-Driven Design (DDD), CQRS, Event Sourcing, Testing, CI/CD und moderne Architekturpatterns.

## Projektziele

Ziel dieses Projekts ist es, Entwickler in die Lage zu versetzen:

- **Domain-Driven Design (DDD) zu verstehen:** Komplexe Geschäftsdomainen effektiv zu modellieren und Anwendungen um Geschäftslogik herum zu strukturieren.
- **CQRS und Event Sourcing umzusetzen:** Lese- und Schreiboperationen zu trennen und ereignisbasierte Persistenz für Skalierbarkeit und Datenrekonstruktion zu nutzen.
- **Codequalität zu verbessern:** Robuste Tests zu schreiben, CI/CD-Pipelines zu implementieren und SOLID-Prinzipien zu folgen.
- **Moderne Architekturen zu übernehmen:** Hexagonale und Clean Architecture Patterns für wartbare, skalierbare und robuste Softwaredesigns anzuwenden.

---

## Funktionen

### 1. Domain-Driven Design (DDD)

- Lernen Sie, **Bounded Contexts** und eine **Ubiquitäre Sprache** zu definieren.
- Modellieren Sie Ihre Geschäftslogik rund um domain-getriebene Services und Entitäten.
- Nutzen Sie NestJS-Module, um spezifische Domains zu trennen und zu kapseln.

### 2. CQRS und Event Sourcing

- Implementieren Sie **Command Query Responsibility Segregation (CQRS)** für die Trennung von Lese- und Schreiboperationen.
- Nutzen Sie **Event Sourcing**, um eine vollständige Historie von Domain-Ereignissen zu speichern.
- Erkunden Sie ereignisgesteuerte Kommunikation zwischen Modulen und Services.

### 3. Fortgeschrittenes Testing und CI/CD

- Schreiben Sie Unit-, Integrations- und End-to-End-Tests für alle kritischen Funktionen.
- Automatisieren Sie Tests mit Tools wie Jest und dem NestJS-Testmodul.
- Implementieren Sie Workflows für Continuous Integration und Continuous Deployment mit GitHub Actions oder ähnlichen Tools.

### 4. Architekturpatterns und Best Practices

- Verstehen und anwenden der **SOLID-Prinzipien** für klareren und wartbaren Code.
- Erkunden Sie **Hexagonale Architektur** und **Clean Architecture** für domain-fokussierte Entwicklung.
- Trennen Sie zentrale Domainlogik von Infrastrukturthemen wie Persistenz oder externen APIs.

---

## Erste Schritte

### Voraussetzungen

- **Node.js:** Installieren Sie Node.js (v14 oder höher).
- **NestJS CLI:** Installieren Sie die NestJS CLI global mit `npm install -g @nestjs/cli`.
- **Datenbank:** Eine laufende PostgreSQL-Instanz oder eine ähnliche Datenbank für die Persistenz.

### Installation

1. Klonen Sie das Repository:

   ```bash
   git clone https://github.com/CCDash-Lerngruppe/NestJS-Advanced-Learning-Project.git
   cd NestJS-Advanced-Learning-Project
   ```

2. Installieren Sie die Abhängigkeiten:

   ```bash
   npm install
   ```

3. Richten Sie die Datenbankverbindung ein:
   - Aktualisieren Sie die `.env`-Datei mit Ihren Datenbankzugangsdaten.
   - Stellen Sie sicher, dass die Datenbank läuft und erreichbar ist.

4. Starten Sie die Anwendung:

   ```bash
   npm run start:dev
   ```

### Nutzung

- API-Dokumentation aufrufen unter `http://localhost:3000/api`.
- Interagieren Sie mit GraphQL unter `http://localhost:3000/graphql`.

---

## Übungen

Dieses Projekt enthält praktische Übungen zu jedem fortgeschrittenen Konzept:

1. **Domain-Driven Design:**
   - Identifizieren Sie Bounded Contexts.
   - Implementieren Sie Services und Module für jeden Kontext.

2. **CQRS und Event Sourcing:**
   - Erstellen Sie Command- und Query-Handler für spezifische Operationen.
   - Implementieren Sie einen einfachen Event Store zur Speicherung und Wiedergabe von Domain-Ereignissen.

3. **Testing und CI/CD:**
   - Schreiben Sie Unit- und Integrationstests für Services und Controller.
   - Konfigurieren Sie eine CI/CD-Pipeline mit GitHub Actions.

4. **Architekturreview:**
   - Refaktorieren Sie ein vorhandenes Modul nach Prinzipien der hexagonalen Architektur.
   - Dokumentieren Sie Ihre Architekturentscheidungen und stellen Sie eine klare Trennung der Verantwortlichkeiten sicher.

---

## Best Practices

- Verwenden Sie **Validation Pipes** zur Validierung von Anfragen.
- Implementieren Sie **Exception Filters** für standardisierte Fehlerbehandlung.
- Befolgen Sie **SOLID-Prinzipien** und stellen Sie eine klare Trennung der Verantwortlichkeiten sicher.
- Nutzen Sie **Event Emitters** oder Message Broker für die Kommunikation zwischen Services in einer Microservice-Architektur.

---

## Mitwirken

Beiträge zu diesem Projekt sind willkommen! Um beizutragen:

1. Forken Sie das Repository.
2. Erstellen Sie einen neuen Feature-Branch:

   ```bash
   git checkout -b feature/ihr-feature-name
   ```

3. Committen Sie Ihre Änderungen:

   ```bash
   git commit -m "Beschreibung Ihres Features"
   ```

4. Pushen Sie auf Ihren Fork:

   ```bash
   git push origin feature/ihr-feature-name
   ```

5. Erstellen Sie einen Pull Request.

---

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz. Details finden Sie in der [LICENSE](LICENSE)-Datei.

---

## Ressourcen

- [NestJS Dokumentation](https://docs.nestjs.com/)
- [Domain-Driven Design von Eric Evans](https://www.domainlanguage.com/)
- [Implementing Domain-Driven Design von Vaughn Vernon](https://vaughnvernon.co/?page_id=168)
- [Event Sourcing Explained](https://martinfowler.com/eaaDev/EventSourcing.html)

---

## Kontakt

Für Fragen oder Feedback kontaktieren Sie uns unter [support@josunlp.de](mailto:support@josunlp.de).
