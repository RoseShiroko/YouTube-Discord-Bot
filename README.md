# 📺 Discord-Youtube-Bot

Ein selbst gehosteter Discord-Bot, der stündlich einen oder zwei YouTube-Kanäle überwacht und neue Videos automatisch in einen gewünschten Discord-Kanal postet.

---

## ✅ Voraussetzungen

1. **Python installieren**  
   Lade [Python](https://www.python.org/downloads/) herunter und **aktiviere beim Installieren "Add Python to PATH"**.

---

## ⚙️ Discord-Bot erstellen und konfigurieren

2. **Entwicklermodus aktivieren:**  
   In Discord unter **Benutzereinstellungen → Erweitert → Entwicklermodus aktivieren**

3. **Gehe zum [Discord Developer Portal](https://discord.com/developers/applications)**  
   - Klicke auf **"New Application"**  
   - Vergib einen Namen

4. **Navigiere zur Rubrik „Bot“**  
   - Aktiviere den Bot sofernes nicht Automatisch Passiert ist.  
   - Setze den Token zurück sofern der Token nicht sichtbar ist.
   - Kopiere den (neuen) Token und füge ihn in die `.env`-Datei ein:
     ```env
     DISCORD_TOKEN=DEIN_DISCORD_BOT_TOKEN
     ```

5. **Navigiere zu „Insterllation" und zu „OAuth2 → URL Generator“**
   - Navigiere zu ***„Insterllation"*** und wähle unter ***„Install Link"*** ***„Discord Provieded Link"*** aus und Kopiere den Link.
   - Navigiere zu ***„OAuth2"*** und füge unter ***„Redirects"*** den gerde Kopierten Link ein.
   - Jetzt wahle unter ***„OAuth2 URL Generator"*** folgendes aus
   - **Scopes:** `bot`  
   - **Bot Permissions:**
     - Manage Roles  
     - Send Messages  
     - Manage Messages  
     - Embed Links  
     - Attach Files  
     - Read Message History  
     - Use External Emojis  
     - Use External Stickers  
     - Change Nickname  
     - View Channels

7. **Installiere den Bot**  
   - Kopiere den generierten Link  
   - Öffne ihn im Browser  
   - Füge den Bot deinem Server hinzu

8. **Bot im gewünschten Kanal berechtigen**  
   - Öffne die Kanaleinstellungen  
   - Unter **Berechtigungen → Rollen/Mitglieder** die Bot-Rolle hinzufügen  
   - Aktiviere:
     - Kanal anzeigen  
     - Nachrichten senden  
     - Links einbetten  
     - Dateien anhängen  
     - Reaktionen hinzufügen  
     - Externe Sticker und Emojis  
     - Nachrichtenverlauf anzeigen  
     - Aktivitäten verwenden  
     - @erwähnen erlauben

9. **🎭 Kanal-ID, Rollen-ID und Rollen Namen kopieren**
    
   ***Kanal-ID***
   - Rechtsklick auf den Kanal → **ID kopieren**  
   - In `.env` eintragen:
     ```env
     DISCORD_CHANNEL_ID=DEINE_KANAL_ID
     ```
     
   ***Rollen-ID***
   - Gehe zu **Servereinstellungen > Rollen**.
   - Rechtsklick auf die **Bot-Rolle** → **"ID kopieren"**.
   - Füge die ID in die `.env`-Datei ein:
     ```env
     Role_ID=ID_der_Discord_Rolle
     ```
  
   ***Rollen-Name***
   - Gehe zu **Servereinstellungen > Rollen**.
   - Bearbeiten der Rolle: **Bot-Rolle** → **"Bearbeiten"**.
   - Füge den Namen in die `.env`-Datei ein:
     ```env
     Bot_Role_Name=Name_der_Discord_Rolle
     ```

## 🎥 YouTube-Kanal-ID finden

9. **YouTube öffnen und gewünschten Kanal aufrufen**  
10. Rechtsklick → **"Seitenquelltext anzeigen"**  
11. STRG + F → Suche nach:
    ```
    content="https://www.youtube.com/channel/
    ```
    → Kopiere die ID, z.B. `UCxxxxxxxxxxxxxxxx`

12. In `.env` einfügen:
    ```env
    CHANNEL_ID=UCxxxxxxxxxxxxxxxx
    ```

13. Optional für zweiten Kanal:
    ```env
    SECOND_CHANNEL_ID=UCxxxxxxxxxxxxxxxx
    ```

---

## 🔑 Google YouTube API einrichten

14. Gehe zur [Google Cloud Console](https://console.cloud.google.com/)  
    - Neues Projekt erstellen  
    - Unter „APIs & Dienste“ → **YouTube Data API v3 aktivieren**

15. Unter „Anmeldedaten“ → **API-Schlüssel erstellen**  
    - Unter **Token bearbeiten** nur **YouTube API** aktivieren  
    - API-Key kopieren und in `.env` einfügen:
      ```env
      YOUTUBE_API_KEY=DEIN_API_KEY
      ```

---

## 🎨 Optional: Statusmeldung anpassen

16. Öffne die Bot-Datei ***(teufelchen_rose_bot.py)*** in einem Texteditor  
    - Finde den Abschnitt mit den Statusmeldungen  
    - Trage eigene ein, z. B.:
      ```python
      "Hört dir zu", "Überwacht YouTube", "Bereit", "Aktiv"
      ```

---

## 🛠️ Bot installieren und starten

17. **Installiere alle Abhängigkeiten automatisch:**  
    Führe die Datei `Installiere benötigte Komponenten automatisch.bat` aus  
    *(Installiert alles aus `requirements.txt`)*

18. **Bot starten:**  
    Doppelklick auf `start.bat`

---

## 🛑 Bot beenden

19. Zum Beenden → `stop.bat` ausführen

20. Wenn du den PC neu startest, musst du `start.bat` erneut manuell ausführen  
    *(Optional: Verknüpfung zu `start.bat` im Windows-Autostart einfügen via `shell:startup`)*

---

## ✅ Der Bot sollte nun:

- Im Discord-Server als Aktiv sichtbar sein  
- Alle 60 Minuten auf neue YouTube-Videos prüfen  
- Neue Uploads im definierten Kanal automatisch posten

---

**Viel Spaß mit dem Bot und Script! 🎉 Bei Fragen oder Fehlern: Gerne Melden!**

---

## ⚠ Planung für ein ein Zukünftiges Update 

- Mehr Status Informationen einfügen mit Zeitsteuerung 
- Unterstützung von mindestens 20 YouTube Kanälen  
- Dynamisch aufgebaut
- Verbesserte Protokolierung und Webhook Statusmeldungen
- Die möglichkeit wenn der BOT startet bereits gesendete Videos nicht erneut zu senden.

---
