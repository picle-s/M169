# 🗒️ Notizen-App mit Markdown und Docker
[TOC]
## 🧠 Projektbeschreibung
Wir entwickeln eine containerisierte Webapplikation zur Erstellung, Anzeige und Verwaltung von Notizen. Die Notizen unterstützen Markdown-Formatierung, um strukturierte Inhalte wie Überschriften, Listen oder Code darzustellen. Das Projekt besteht aus mehreren Docker-Services, die gemeinsam auf einer AWS-Instanz betrieben werden.

Im Backend werden die Notizen gespeichert und verarbeitet. Die Datenbank sorgt für die dauerhafte Ablage, und ein Webserver übernimmt die Auslieferung der Weboberfläche. Das Projekt dient als praktisches Beispiel für Infrastructure as Code (IaC) mit Docker.

## 🌟 Ziele (SMART formuliert)

### Ziel 1: Docker-Setup mit allen Services
Bis zum 5. April erstellen wir ein `docker-compose.yml`, das alle benötigten Services (App, Datenbank, Webserver) zuverlässig startet. Die App ist dann im Browser über die AWS-IP erreichbar.

### Ziel 2: Markdown-Integration
Spätestens bis zum 10. April ermöglichen wir es, Notizen im Markdown-Format einzugeben und korrekt formatiert anzuzeigen (z. ​​z. B. mit `marked.js` im Frontend oder `markdown` im Backend).

### Ziel 3: Persistente Datenspeicherung
Bis zum 7. April richten wir ein Docker-Volume für die Datenbank ein, damit Notizen auch nach einem Neustart der Container erhalten bleiben.

## 🧱 Technischer Aufbau

### 🔹 Services
- **App-Container**: Backend-Logik zur Verwaltung der Notizen (z. B. in Python/Node.js)
- **Datenbank-Container**: PostgreSQL zur Speicherung der Notizen
- **Webserver-Container**: Nginx für die Auslieferung der Weboberfläche

### 🔹 Datenbank
Wir verwenden PostgreSQL als Datenbank. Sie wird als Container betrieben und speichert Titel, Inhalt und Zeitstempel der Notizen. Die Daten sind persistent über ein Docker-Volume.

### 🔹 Docker
Alle Komponenten laufen in Containern. Die Orchestrierung erfolgt über `docker-compose`, womit das Projekt einfach auf jeder Umgebung reproduzierbar ist.

## 📁 Repository-Struktur (Beispiel)

```
Projekt👍/
├── backend/
│   └── app.py
├── frontend/
│   └── index.html
├── docker-compose.yml
├── README.md
└── docs/
    └── projektbeschreibung.md
```

## 🛡️ Sicherheit
- Container laufen nicht als Root
- Nur notwendige Ports sind freigegeben
- Datenbank ist nur intern erreichbar
- Optional: Benutzer-Authentifizierung in der App

## 📝 Dokumentation
Die gesamte Projekt-Dokumentation erfolgt in Markdown und ist im GitLab-Repository versioniert. Änderungen werden mit sinnvollen Commits nachvollziehbar gemacht.
### Datenbank Struktur
Unsere Datenbank wird nach dem aktuellen Stand 2 Tabellen haben;
1. **User Tabelle**: Diese Tabelle enthält alle Informationen zu den Benutzern die unsere Applikation verwenden werden.
   1. **ID**: Wird verwendet um die einzelnen Benutzern unterscheiden zu können. Die IDs sind Einzigartig
   2. **Benutzername**: Da IDs unschön sind, kann jeder Benutzer sich ein Benutzername erstellen, da wir schon IDs haben, können mehrere Benutzer den selben Namen haben.
   3. **Createt at**: Für Administrative Gründe, ist es noch hilfreich um zu sehen, wann ein Benutzer erstellt worden ist.
   4. **Passwort**: Damit die Benutzer sich sicher anmelden können, hat jeder Benutzer ein Passwort das in der Datenbank geshashed gespeichert wird.
2. **Notizen Tabelle**: Diese Tabelle wird für das Speichern von den Notizen verwendet.
   1. **ID**: Um Notizen zu Identifizieren, gibt es eine Eindeutige ID für jede  Notiz
   2. **user-ID**: Damit die Notizen den Benutzern zugeteilt werden können, werden Benutzer IDs auch gespeichert. Kann sein das wird später noch multi-User Notizen erlauben.
   3. **Title**: Jede Notiz wird auch einen Titel haben
   4. **Inhalt**: Der Inhalt einer Notiz muss logischerweise auch gespeichert werden.
## 🚀 Ausführung
Das Projekt wird auf einer AWS-Instanz entwickelt. Wir verwenden einen gemeinsamen Benutzeraccount für den Zugriff, da es sich um ein Schulprojekt ohne besondere Sicherheitsanforderungen handelt.

