# PatientPoint - Docker Compose Setup

Dieses Repository enthält die **Docker Compose** Konfiguration zum lokalen Self-Hosting der PatientPoint-Anwendung. Die Anwendung besteht aus einem Angular-Frontend und zwei Backend-Services:

- **Core Service:** Verantwortlich für zentrale Funktionen wie Authentifizierung, RFID-Chip-Zuweisung, Menüplanverwaltung und Logging.
- **FHIR Service:** Simuliert FHIR-Ressourcen (Patient, Appointment, Practitioner) zur Integration mit KIS-artigen Daten.

PatientPoint richtet sich an Patienten in den Vamed-Reha-Zentren, die vor Ort Informationen zu Terminen und Speiseplänen abrufen können – insbesondere über einen RFID-basierten Anmeldeprozess.

## Projekt Zusammenfassung

PatientPoint bietet eine modulare, containerisierte Lösung zur Bereitstellung eines Patienten-Kiosk-Systems in den Vamed-Reha-Zentren. Das System umfasst ein modernes Angular-Frontend sowie zwei spezialisierte Backend-Services für Kernfunktionalitäten und FHIR-Simulation. Dieses Repository ermöglicht es Entwicklern, das komplette System via Docker Compose lokal oder in der Cloud zu deployen und zu testen.

## Voraussetzungen

- **Docker & Docker Compose:**  
    Stelle sicher, dass Docker und Docker Compose auf deinem Entwicklungssystem installiert sind.

## Lokaler Start

1. **Klonen des Repositories:**
    ```bash
    git clone https://github.com/meyremmc/patient-point-docker.git
    cd patient-point-docker
    ```
    
2. **Container starten:**
    ```bash
    docker-compose up -d
    ```
    
3. **Zugriff:**
    - **Frontend:** [http://localhost:4200](http://localhost:4200)
    - **Core Service API:** [http://localhost:8080](http://localhost:8080)
    - **FHIR Service API:** [http://localhost:8081](http://localhost:8081)

- ## Architekturübersicht

![Image](https://github.com/user-attachments/assets/41c449cb-a9ea-4868-adc5-378a9e4604b5)

- **Frontend (Angular):**  
    Entwickelt als Single-Page-Application (SPA) und im Kiosk-Modus betrieben, sodass die Anwendung hardwareunabhängig ist.  
    _Technologien:_ Angular, TypeScript, SCSS
- **Core Service:**  
    Implementiert zentrale Geschäftslogik, u.a. Authentifizierung via RFID, Benutzer- und Chipmanagement, Menüplanverwaltung sowie Logging.  
    _Technologien:_ Java (Spring Boot), Maven & PostgreSQL 
- **FHIR Service:**  
    Stellt Dummy-FHIR-Ressourcen bereit, um typische KIS-Funktionalitäten zu simulieren.  
    _Technologien:_ Java (Spring Boot), Maven & PostgreSQL
    