# Universal Backup Installer (RAR + optional SQL)

Dieses Repository enthält ein universelles **Backup-Skript für Windows-Server**, das sowohl Ordner als auch optional eine MySQL/MariaDB-Datenbank sichern kann.  
Die Backups werden als **.rar** komprimiert und automatisch in der **Windows Aufgabenplanung** (Task Scheduler) täglich ausgeführt.

---

## Features
- 📁 Sichert beliebige Ordner (z. B. FiveM-Server)
- 🗄️ Optional: SQL-Dump einer Datenbank (MySQL/MariaDB via `mysqldump`)
- 📦 Packt alles in ein **.rar**-Archiv (inkl. SQL-Dump)
- 🧹 Löscht alte Backups automatisch (Retention in Tagen einstellbar)
- ⏰ Einrichtung einer täglichen Aufgabe in der **Windows Aufgabenplanung**
- 📝 Logs mit allen Backup-Details

---

## Installation & Nutzung

### 1. Repository klonen oder Dateien herunterladen
Speichere die Datei **install-universal-backup.bat** auf deinem Windows-Server, z. B. nach:

### 2. Script starten
- Rechtsklick → **Als Administrator ausführen**
- Fragen beantworten:
  - Quellordner (z. B. `C:\FiveM - Server\Riveria Online`)
  - Backup-Ziel (z. B. `C:\Backups\RiveriaOnline`)
  - Pfad zu `rar.exe` (Standard: `C:\Program Files\WinRAR\rar.exe`)
  - Optional: DB-Backup aktivieren, Pfade zu `mysqldump.exe` und `mysql.exe` angeben (Standard: `C:\xampp\mysql\bin\...`)
  - DB-Name, User (Standard `root`), Passwort
  - Uhrzeit für tägliches Backup
  - Task-Name

### 3. Automatische Einrichtung
Das Script erzeugt automatisch:
- ein ausführbares Backup-Script `backup-run.bat`
- eine geplante Aufgabe im **Task Scheduler** (läuft als `SYSTEM` täglich um die eingestellte Uhrzeit)

---

## Ergebnis
- Backups liegen standardmäßig unter:
