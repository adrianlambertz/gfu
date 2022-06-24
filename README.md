
## TAG 1

**Schwerpunkte: Intro, Vorstellung, WordPress-Backups und erste Schritte bei WordPress-Absicherung**

*Vormittag / Früher Nachmittag:*
- Kurze Vorstellungsrunde zum Kennenlernen
- Allgemeine Fragerunde: Skills, Erwartungen, Anforderungen
- Anmelden auf Test-WordPress Installation und erste SSH Verbindung auf dem Testserver
- Einführung in WordPress Backups
- Installation und Erklärungen des "Updraft Plus" Plugins
- Installation und erste Konfiguration von "rsnapshot" auf dem Server 
- Erläuterung der Vor und Nachteile von Plugin Lösungen und serverseitigen Lösungen

*Nachmittag:*
- Einführung in WordPress Absicherung
- Wo beginnt Security? Wahl des Hosters/Servers, der Plugins & des Themes
- Login absichern: Einrichtung einer "Zwei Faktor Authentifizierung"
- Installation und Erläuterungen zu WordFence Security & iThemes Security

**Tagesziel: WordPress Backups laufen, rsnapshot ist als inkrementelles Backup aufgesetzt. Grundlagen zur Security erläutert und erste Security-Maßnahmen wurden durch Plugins ergriffen zur Vorbereitung auf Tag 2**

## TAG2

**Schwerpunkte: WordPress Absicherung: Serverseitige Absicherung, anhand von praktischen Beispielen Angriffe & Hacks erkennen, verhindern und aufräumen. Best Practices bei Programmierung**

*Ganztägig:*
- verschiedene Optionen und Maßnahmen von iThemes Security direkt auf Serverebene einbauen
- Deaktivierung bekannter Einfallstore (xmlrpc, PHP Ausführung in uploads etc.)
- Klassische Angriffsvektoren in Serverprotokollen (Logs) ausmachen und verhindern
- Fail2Ban als Logauswertung hinzuziehen zur Analyse und Aussperrung von IP-Adressen
- Vorstellung des serverseitigen ISPProtect Malware Scanners
- Schutz vor Denial-Of-Service-Attacken (DDOS) via Cloudflare-CDN
- Security im Theme- und Plugin-Kontext: Escaping und Sanitizing der eigenen  Programmierung

**Tagesziel: die WordPress Installation wurde direkt auf Serverebene abgesichert, wir haben Angriffsmuster in den Serverlogs ausmachen können und per Fail2ban eine effiziente Lösung zum Abwehren dieser Attacken implementiert. Ausserdem können wir mit dem Malware Scanner Infektionen finden und bereinigen. Best practices für die Theme- & Pluginprogrammierung wurden ebenfalls erläutert.**

##  TAG 3

**Schwerpunkte: WordPress automatisieren & beschleunigen**

*Vormittags:*
- Vorstellung von WP-CLI und einfacher Befehle zum Suchen & Ersetzen in der DB, Updates einspielen, etc.
- Vorstellung eines simplen Bash Scripts zur Installation und Einrichtung eines WordPress
- Automatisierung per Server Cronjob

*Vormittags/Nachmittags:*
- WordPress beschleunigen mittels Caching: Cachify & WP Rocket vorstellen und vergleichen
- Weitere Performance Optimierungen auf Serverebene
- Grobe Erklärungen zum Tuning von Apache, PHP und MySQL

**Tagesziel: wir können mit praktischen WP-CLI Befehlen das WordPress automatisiert warten, wir haben mit einem simplen Bashscript innerhalb von Minuten ein WordPress installiert und vorkonfiguriert. Wir haben die Geschwindigkeit der WordPress Installation durch Caching massiv erhöht.**
