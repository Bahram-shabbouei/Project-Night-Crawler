🛠️ Projekt Night-Crawler – Backend-Dokumentation

📁 Projektstruktur:

Das Backend befindet sich im Ordner backend. Es enthält folgende Hauptdateien:
server.py – Hauptserver der Anwendung (Flask)

- crawler_api_baa.py – API-Anbindung an die Jobbörse der Bundesagentur für Arbeit
- crawler_stepstone.py – optionaler Crawler für StepStone (derzeit evtl. deaktiviert)
- mongodb_connect.py – Verbindungslogik zur MongoDB-Datenbank
- .env.example – Beispiel für Umgebungsvariablen
- requirements.txt – alle Python-Abhängigkeiten für das Backend

⚙️ Benötigte Abhängigkeiten:

- Flask
- flask-cors
- flask-mail
- flask-dotenv
- python-dotenv
- requests
- pymongo
- apscheduler
- bs4

📝 Diese findest du in der Datei requirements.txt im backend-Ordner.


📦 Installation der Abhängigkeiten:

Python-Umgebung aktivieren:
- venv\Scripts\activate (Windows)

Installiere alle benötigten Pakete:
- pip install -r backend/requirements.txt

🔐 .env-Datei erstellen:
Lege im Projektverzeichnis (Root) eine Datei namens .env an. Diese sollte die API-Schlüssel und Zugangsdaten enthalten, wie im 

Beispiel:
MAIL_PORT=587  
MAIL_SERVER=smtp.example.com  
MAIL_USERNAME=your_email@example.com  
MAIL_PASSWORD=your_password  
MAIL_DEFAULT_SENDER=your_email@example.com  

BAA_API_KEY=your_api_key  
MONGO_URI=mongodb+srv://dein_uri 

📄 Eine .env.example liegt im Projekt bereit und dient als Vorlage.

🚀 Backend starten:

Du startest den Flask-Server nicht im backend-Ordner, sondern im Root-Verzeichnis mit folgendem Befehl:
- python backend/server.py

📡 Der Server läuft dann unter http://127.0.0.1:5000 (oder wie in server.py konfiguriert).

🧪 Funktionen des Backends:

- 🔎 /jobsuchen_baa – Sucht Jobs via Bundesagentur-API anhand von Keywords, Ort & Radius
- 💾 /update_bookmark – Speichert/aktualisiert Bookmarks in MongoDB
- 🔁 Automatisches Speichern neuer Jobs mit eindeutiger UUID
- 📧 Optionale E-Mail-Funktion mit Mail-Konfiguration

🧹 Hinweis zur Projektstruktur
__pycache__ ist in .gitignore eingetragen und wird nicht getrackt

Temporäre oder sensible Dateien sollten ebenfalls ausgeschlossen werden

✅ Status:

- Backend funktionsfähig
- .env-Konzept implementiert
- MongoDB-Anbindung stabil
- API-Anbindung zur Arbeitsagentur aktiv
- Weitere Quellen und Automatisierungen in Arbeit
