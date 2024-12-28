# vaccinaion-tracker-web-app-v1.0


### Was diese `README.md`-Datei abdeckt:
1. **Projektübersicht**: Eine klare Einführung in das Projekt und seine Kernfunktionen.
2. **Installations- und Ausführungshinweise**: Anleitungen zur Installation und Ausführung des Backends und Frontends.
3. **Bekannte Probleme und Lösungshinweise**: Eine Beschreibung des bekannten Problems mit den Impfmethoden im Frontend und eine Erklärung, dass daran gearbeitet wird.
4. **API-Endpunkte**: Eine Übersicht der wichtigsten Endpunkte des Backends.
5. **Swagger**: Beispiele-Requests.

P.S. Die restliche FrontEnd-Datei ist zu groß, aber der Haupt-Code ist unter "src" enthalten.

Diese `README.md`-Datei sollte dir helfen, den aktuellen Stand des Projekts zu verstehen und es korrekt auszuführen.

Die Vaccination Tracker Web App ist eine Webanwendung zur Verwaltung von Impfungen, die es Nutzern ermöglicht, ihre Impfdaten zu verfolgen und zu verwalten. Die Anwendung besteht aus einem Backend und einem Frontend, das noch in der Entwicklungsphase ist. Die Kernfunktionen umfassen:

Registrierung & Login: Nutzer können sich registrieren und einloggen.
Persönliche Daten: Nutzer können ihre persönlichen Daten eingeben und ändern.
Impfdaten: Nutzer können Impfdaten eingeben, anzeigen und ändern.
Benachrichtigungen: Nutzer werden benachrichtigt, wenn ihre Impfung ausläuft.
Das Backend der Anwendung ist in .NET 6 entwickelt und verwendet Entity Framework Core zur Datenbankanbindung. Um das Backend lokal auszuführen, müssen .NET 6 oder höher und eine Datenbank (z. B. SQL Server) installiert sein. Nachdem das Projekt geklont wurde, können die Abhängigkeiten mit dotnet restore installiert und die Datenbankmigrationen mit dotnet ef database update durchgeführt werden. Der Server kann mit dotnet run gestartet werden.

Die API-Endpunkte im Backend umfassen:

POST /auth/register – Registrierung eines neuen Benutzers.
POST /auth/login – Login und Rückgabe eines JWT-Tokens.
GET /User - für UserData Abrufe
POST /User - für UserData Bearbeitung
GET /vaccine/{userId} – Abrufen aller Impfstoffe für einen bestimmten Benutzer.
POST /vaccine – Hinzufügen einer neuen Impfstoff.
GET /vaccination/{userId} – Abrufen aller Impfungen für einen bestimmten Benutzer.
POST /vaccination – Hinzufügen einer neuen Impfung.
PUT /vaccination - Änderung einer Impfung.
DELETE /vaccination - Löschen einer Impfung.


Das Frontend ist mit React und TypeScript entwickelt und verwendet npm zur Verwaltung der Abhängigkeiten. Nach dem Klonen des Repositories wird npm install ausgeführt, um die Abhängigkeiten zu installieren, und npm start startet die Entwicklungsumgebung. Das Frontend ermöglicht es den Nutzern, ihre Impfungen einzugeben, anzuzeigen und zu bearbeiten.

Aktuell gibt es ein Problem mit dem GET /vaccination/{userId}-Endpunkt, das nach einer Änderung im Backend aufgetreten ist. Dieser Endpunkt gibt derzeit einen Fehlerstatus 500 zurück, da die Vaccination-Methoden im Backend geändert wurden. Das Frontend funktionierte zuvor fehlerfrei, aber durch die Änderungen im Backend müssen diese Methoden im Frontend angepasst werden. Das Problem wird derzeit verfolgt.

Trotz dieses Problems funktioniert die grundlegende Logik für Registrierung, Login und die Impfdatenverwaltung. Weitere Funktionen wie Benachrichtigungen, die Nutzer warnen, wenn ihre Impfung ausläuft, sind noch in der Entwicklung.

Für Entwickler, die zum Projekt beitragen möchten, wird empfohlen, das Repository zu forken und Pull-Requests für neue Funktionen oder Fehlerbehebungen zu erstellen.

Das Projekt befindet sich noch in der Entwicklungsphase, daher können noch Fehler auftreten, aber das Team arbeitet daran, diese zu beheben.

Post User: 
{
  "email": "test@test.de",
  "passwordHash": "123",
  "firstName": "Max",
  "lastName": "Mustermann",
  "street": "Musterstraße",
  "houseNumber": "123",
  "zipCode": "12345",
  "city": "Musterstadt",
  "phoneNumber": "0123456789",
  "healthInsurance": "MusterKasse",
  "insuranceType": 1
}


Post Vaccine:
{
  
  "name": "TestVaccine",
  "producer": "asd",
  "vaccineType": 1,
  "vaccinationType": "asd",
  "requiredDoses": 2,
  "vaccinations": [
    
  ],
  "userId": 1,
  "user": {
   
    "vaccinations": [
      
    ]
  }
}


Post Vaccination:
{
  
  "vaccinationDate": "2024-12-27T23:26:56.969Z",
  "doctorName": "Dr.Test",
  "boosterDate": "2024-12-30T23:26:56.969Z",
  "serialNumber": "string",
  "manufacturingDate": "2024-12-27T23:26:56.969Z",
  "userId": 1,
  "user": {
    
    "vaccinations": [
      
    ]
  },
  "vaccineId": 4,
  "vaccine": {
    
    "vaccinations": [
      
    ],
    "userId": 1,
    "user": {
      
      "vaccinations": [
        
      ]
    }
  }
}






