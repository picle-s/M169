# KN02

# Teil 1  

#### Challange 1
1. Hosting von Virtuellen Machinen gehört zu **IaaS**
2. Nutzung von Google Docs gehört zu **SaaS**
3. Die Containerverwaltung mit Kubernetis gehört zu **CaaS**

#### Challange 2
- **IaaS**
IaaS stellt Virtuelle Machinen bereit, mit SPeicherplatzt, Netzwerk und andere IT-infrastrucktur Sachen.
Der Benutzer ist nicht zuständig für die Verwaltung von Hardware, aber alels was auf der Machine passiert. ALso Betriebsystem und mehr.
Beispiele: **AWS EC2**
- **PaaS**
PaaS bietet hingegen eine vollständige Entwicklungsumgebung bereit.
Der Bentutzer 
## Vergleich
| Aspekt | IaaS | PaaS |
| --------- | ---- | ---- |
| Verwaltung der Infrastruktur | Benutzer                       |Cloud-Anbieter                        |
| Betriebssystempflege         | Benutzer                       | Cloud-Anbieter                        |
| Skalierung & Ressourcen      | Manuell durch Benutzer         | Automatisiert durch Cloud-Anbieter    |
| Hauptnutzer                  | Systemadministratoren, DevOps  | Entwickler, Software-Teams            |
| Beispiel                     | AWS EC2, Google Compute Engine | Google App Engine, Azure App Services | 

# Teil 2

## Teil 2 Aufgabe 1

### **Vorteile der automatischen Konfiguration**

- Konsistenz & Wiederholbarkeit
- Zeitersparnis & Skalierbarkeit
- Reduzierung menschlicher Fehler
- Versionierbarkeit & Nachvollziehbarkeit

### **Infrastructure as Code (IaC)**

IaC bedeutet, IT-Infrastruktur per Code zu verwalten und bereitstellen, anstatt manuell zu konfigurieren.

**Vorteile:**

- Automatisierte Bereitstellung
- Skalierbarkeit & Portabilität
- Versionierte Verwaltung

## Teil 2 Aufgabe 2

Tools für IaC

#### Docker

- Containerisierung von Anwendungen
- Portabilität & Ressourcenschonung

**Use-Case:**

- Bereitstellung von Microservices

#### Terraform

- Verwaltung von Infrastruktur als Code
- Multi-Cloud-Support

**Use-Case:**
- Automatische Cloud-Bereitstellung

### Kubernetes & Container-Orchestrierung

#### Kubernetes

- Automatisierte Verwaltung von Containern
- Skalierung & Selbstheilung

**Use-Case:**
- Verwaltung von Microservices

#### Container-Orchestrierung

- Verwaltung großer Container-Umgebungen
- Automatische Skalierung & Fehlerbehebung

**Beispiele:**
- Kubernetes, Docker Swarm

## Teil 3

### Aufgabe 1


| Cloud-Anbieter |Regionen | Verfügbarkeitszonen |
|---|----|-----|
| AWS |36 | 114 |
| Azure  | 64 |1-3 pro Region|
| GCP |41  |124|



**AWS**
 
Amazon S3 (Simple Storage Service): Ermöglicht kostengünstige und skalierbare Datenspeicherung mit hoher Verfügbarkeit.
 
**Azure**
 
Azure Blob Storage: Skalierbarer Objektspeicher für unstrukturierte Daten.
 
**GCP**
 
Cloud Storage: Einheitliche Speicherlösung für strukturierte und unstrukturierte Daten.