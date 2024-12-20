# Zusatzteil: Fortgeschrittene Architekturen und Praktiken mit NestJS

## Lernziele des Zusatzteils

- **Domain-Driven Design (DDD)**: Du verstehst, wie du komplexe Fachdomänen in handhabbare Module zerlegst und damit langfristig wart- und erweiterbare Systeme entwickelst.
- **CQRS und Event Sourcing**: Du lernst, wie du Lese- und Schreiboperationen trennst (CQRS) und wie Event Sourcing als alternatives Persistenzmuster genutzt werden kann.
- **Fortgeschrittenes Testen & CI/CD**: Du erfährst, wie du deine Anwendungen umfassend testest (Unit-, Integration-, End-to-End-Tests) und durch kontinuierliche Integration und Deployment robust in den Produktionsbetrieb bringst.
- **Architekturmuster & Best Practices**: Du bekommst einen Überblick über SOLID-Prinzipien, Hexagonale Architektur und Clean Architecture und wie du diese mit NestJS umsetzen kannst.

---

## Theoretischer Teil

### Domain-Driven Design (DDD)

**Was ist DDD?**  
DDD ist ein Ansatz, um komplexe Softwareprojekte stark an der Fachlichkeit („Domäne“) auszurichten. Statt sich vorrangig an technischen Strukturen zu orientieren, modelliert man die Software eng entlang fachlicher Konzepte, Begriffe und Prozesse.

**Zentrale Konzepte:**

- **Domain**: Der fachliche Kernbereich, z. B. der Bestellprozess eines Onlineshops.  
- **Ubiquitous Language**: Gemeinsame Sprache aller Beteiligten (Entwickler, Domänenexperten, Stakeholder).  
- **Bounded Contexts**: Abgegrenzte Teilbereiche der Domäne, in denen Begriffe und Modelle eindeutig definiert sind, z. B. „Billing“ oder „Shipping“.

**NestJS-Integration:**

- Unterteile deine Anwendung in Module, die jeweils einen Bounded Context repräsentieren.  
- Verwende Services und Entities als domänenzentrische Bausteine, die eng am Fachmodell ausgerichtet sind.

---

### CQRS (Command Query Responsibility Segregation)

**Idee**:  
Trenne Lese- und Schreibzugriffe auf dein System in separate Modelle. Commands ändern den Zustand, Queries lesen Daten aus. Das ermöglicht Skalierung und Optimierung beider Zugriffsarten unabhängig voneinander.

**Beispiel:**

- **Command Handler**: Verarbeitet ein `CreateOrderCommand`, legt eine neue Bestellung an.  
- **Query Handler**: Verarbeitet ein `GetOrdersQuery`, liest Bestellungen aus einer optimierten Lesedatenbank aus.

**NestJS-Integration:**

- Nutze separate Handler-Klassen für Commands und Queries.  
- Verwende Messaging oder EventBus-ähnliche Patterns von NestJS, um Command- und Query-Handler zu registrieren.

---

### Event Sourcing

**Was ist Event Sourcing?**  
Statt den aktuellen Zustand einer Entität zu speichern, zeichnest du alle Ereignisse (Events) auf, die zur aktuellen Situation führten. Der Zustand wird aus diesen Events rekonstruiert.

**Vorteile:**

- Vollständige Historie aller Änderungen.  
- Leichtere Implementierung von Audits, Replays und komplexen Analysen.

**NestJS-Integration:**

- Nutze Event-Handler, um Events zu verarbeiten und in einer Event Store-Datenbank (z. B. EventStoreDB) zu speichern.  
- Rehydrate Aggregate aus den gespeicherten Events, um den aktuellen Zustand zu erhalten.

---

### Fortgeschrittenes Testen & CI/CD

**Test-Typen:**

- **Unit-Tests**: Testen einzelne Klassen und Methoden isoliert.  
- **Integrationstests**: Testen das Zusammenspiel mehrerer Komponenten, z. B. Controller + Service + Datenbank.  
- **E2E-Tests**: Prüfen das gesamte Systemend-to-end, z. B. über HTTP-Requests an die laufende Anwendung.

**Tools & Best Practices:**

- Nutze `@nestjs/testing` und Jest für Unit- und Integrationstests.  
- Automatisiere Tests mit CI-Tools (GitHub Actions, GitLab CI, Jenkins).  
- Stelle sicher, dass bei jedem Commit Tests laufen und bei Fehlern kein Deployment erfolgt.

---

### Architekturmuster & Best Practices

**SOLID-Prinzipien**:  

- Single Responsibility Principle, Open/Closed Principle, usw.  
- Helfen dabei, Code sauber, erweiterbar und verständlich zu halten.

**Hexagonale Architektur**:  

- Entkoppelt die Domänenlogik von technischen Details (Datenbanken, Web Frameworks).  
- Ermöglicht einfache Austauschbarkeit von Adaptern (z. B. Datenbankimplementierung).

**Clean Architecture**:  

- Schichtentrennung in Entities, Use-Cases, Interface Adapters, Frameworks.  
- Minimiert Abhängigkeiten von äußeren Schichten, fokussiert auf Kernlogik.

In NestJS kann man diese Prinzipien adaptieren, indem man:

- Strikte Modul- und Service-Grenzen einhält.  
- Die Domäne klar von Infrastruktur-Code (z. B. Repositories, Gateways) trennt.  
- Adapter-Pattern nutzt, um externe Systeme anzubinden.

---

## Praktischer Teil

### 1. **DDD-Übung:**

- Identifiziere einen komplexen Fachbereich deiner bestehenden Anwendung.  
- Definiere die Bounded Contexts (z. B. „Billing“ vs. „Shipping“) und strukturiere deine Module entsprechend um.  
- Schreib eine Ubiquitous Language-Dokumentation, um sicherzustellen, dass alle Beteiligten dieselben Begriffe nutzen.

### 2. **CQRS & Event Sourcing:**

- Teile für einen Anwendungsfall (z. B. Bestellung anlegen, Aufträge abrufen) Commands und Queries auf.  
- Implementiere einen `CreateOrderCommandHandler` und einen `GetOrdersQueryHandler`.  
- Experimentiere mit einem einfachen Event Store: Speichere `OrderCreated`-Events und lade den Zustand neu, um dir das Prinzip des Event Sourcing vor Augen zu führen.

### 3. **Erweiterte Tests & CI/CD:**

- Schreibe mehrere Unit-Tests für deine Domain-Services.  
- Erstelle Integrationstests, die einen ganzen Request-Response-Zyklus (inklusive Datenbank) prüfen.  
- Konfiguriere eine GitHub Actions Workflow-Datei, die bei jedem Push die Tests ausführt und nur bei Erfolg einen Merge zulässt.

### 4. **Architektur-Review:**

- Überprüfe deinen Code auf SOLID-Konformität: Wo könntest du Verantwortlichkeiten klarer trennen?  
- Evaluiere, wie du hexagonale Architekturprinzipien anwenden kannst: Welche Teile deines Codes sollten in den Domänenkern verschoben werden und welche gehören zu den Adaptern?  
- Diskutiere intern oder dokumentiere deine Architekturentscheidungen und halte sie für die Weiterentwicklung fest.

---

## Zusammenfassung

In diesem Zusatzteil hast du gelernt:

- Wie du komplexe fachliche Anforderungen mithilfe von DDD abbilden kannst.
- Wie du durch CQRS und Event Sourcing flexiblere, skalierbare und historisierbare Systeme aufbaust.
- Wie du durch umfassendes Testen und CI/CD einen hohen Qualitätsstandard sicherst und das Risiko beim Deployment minimierst.
- Wie fortgeschrittene Architekturmuster und Best Practices dabei helfen, langfristig wartbare, erweiterbare und robuste Systeme zu entwickeln.

Damit verfügst du nun über ein tiefgreifendes Verständnis für moderne Backend-Architekturen und deren Umsetzung mit NestJS. Dieses Wissen gibt dir die Werkzeuge an die Hand, um auch in komplexen Projekten saubere, skalierbare und zuverlässige Softwarelösungen zu erstellen.

---

## Weiterführende Ressourcen (fakultativ)

- Eric Evans: *Domain-Driven Design: Tackling Complexity in the Heart of Software*  
- Vaughn Vernon: *Implementing Domain-Driven Design*  
- NestJS Community Blog und Beispielprojekte zu CQRS & Event Sourcing  
- [NestJS – CQRS Module](https://docs.nestjs.com/recipes/cqrs)  
- EventStoreDB oder Axon Framework für Event Sourcing-Praktiken

Diese Ressourcen vertiefen dein Wissen in den vorgestellten Themen und helfen dir, komplexe Anforderungen professionell umzusetzen.
