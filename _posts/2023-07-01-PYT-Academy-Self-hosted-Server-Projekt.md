---
title: PYT-Academy Self hosted Server Projekt
date: 2023-07-18 12:00:00 -0300
last_modified_at: 2023-07-22 13:32:00 -0300
categories: [Projekte, Server]
tags: [open-source, Self-hosted, Server, Projekt, Cloud, Verein]
author: david
pin: true
---

Hallo Team, 
Lasst uns an den Aufbaudiagramm arbeiten. Hier der Chatverlauf für weiterführende Informationen

> [Chatverlauf ChatGPT](https://chat.openai.com/share/5a6b8490-468f-4960-89b4-9ff8ea1c5178){:target="_blank"}
{: .prompt-tip }

Hier das Diagramm. Es fehlen noch sämtliche Verbindungen und Anschlüsse und schaut mal ob ich alle Anwendungen und Hardware erfasst habe. Auch die Jetzigen Anschlüsse müssen definiert werden. Welche Anschlüsse der Mac Mini hat teile ich weiter unten

![Test Diagram](/assets/draw/PYT-Server.svg)

# Gesprächpunkte

1. [Cloud-Speicher](#cloud)
Wir haben die Absicht, einen Cloud-Speicher für unseren Verein einzurichten. Angesichts unserer Anforderungen und Nutzungsvolumens, haben wir vorläufig eine Speichergröße von 250 bis 500GB ins Auge gefasst. Details zur Umsetzung müssen noch geklärt werden.

2. E-Mail-Server
Wir planen, einen E-Mail-Server für unseren Verein aufzusetzen. Die Einzelheiten dazu wurden während des Gesprächs nicht weiter ausgeführt und bedürfen weiterer Recherche und Planung.

3. Passwortmanagement
Wir haben die Idee eines Passwortmanagement-Systems in Betracht gezogen. Allerdings sind die Details zu dieser Anwendung noch unklar und müssen noch erörtert werden.


## Status
Wir sind derzeit dabei, verschiedene Cloud-Speicher-Softwarelösungen zu überprüfen. Nachdem wir unsere Anforderungen analysiert haben, haben wir vier vielversprechende Optionen ins Auge gefasst: ownCloud, Nextcloud, Pydio und Seafile. Wir testen und bewerten diese Plattformen, um ihre Sicherheit, Datenschutzfunktionen und Leistung zu prüfen. Unser Fokus liegt darauf, die beste Lösung für unsere Bedürfnisse zu finden.

## Ziel
Unser Hauptziel ist es nicht, Gewinn zu erzielen, sondern das Projekt als Lern- und Übungsmöglichkeit zu sehen. Wir möchten jedoch auch unsere Dienste einer kleinen Gruppe anbieten und so unsere Vereinskasse für weitere Projekte und Investitionen aufbessern.

### Wie entscheiden wir uns für unser software?
Bei der Evaluierung von Softwarelösungen liegt unser besonderer Fokus auf Sicherheit, Datensicherheit und der Einhaltung von *Datenschutzrichtlinien*. Wir setzen auf *Open-Source-Software*, um Transparenz, Flexibilität und die Unterstützung einer engagierten Community sicherzustellen. Neben der *Kompatibilität mit verschiedenen Betriebssystemen* bewerten wir *Benutzerfreundlichkeit*, *Skalierbarkeit* und Sicherheitsfunktionen wie *Verschlüsselung*, *Zugriffskontrolle* sowie die Implementierung von *2FA (Two-Factor Authentication) und MFA (Multi-Factor Authentication)* als zusätzliche Sicherheitsmaßnahmen. Darüber hinaus achten wir darauf, dass die Software den Anforderungen und Vorschriften der *Datenschutzgesetzen* entspricht. Unsere Zielsetzung ist es, eine umfassende Sicherheitsarchitektur bereitzustellen, die die Vertraulichkeit, Integrität und der Benutzerdaten gewährleistet. Wir suchen nach einer Softwarelösung, die unseren hohen Standards in Bezug auf Sicherheit, Datensicherheit, *2FA* und *MFA* entspricht und den geltenden Datenschutzrichtlinien entspricht.

## Besonderheiten:
Wir haben darüber beraten, uns durch bestimmte Alleinstellungsmerkmale von großen Unternehmen abzuheben. Diese sind: hohe Sicherheit, persönlicher Kontakt und exzellenter Service.

## Cloud

Die Auswahl der richtigen Cloud-Speicher-Software für einen Server kann eine herausfordernde Aufgabe sein. Wir haben uns verschiedene Optionen angesehen und möchten in diesem Artikel ownCloud, Nextcloud, Pydio und Seafile vergleichen. Hier sind unsere Notizen zu den jeweiligen Lösungen:

### ownCloud
ownCloud scheint auf den ersten Blick eine gute Wahl zu sein. Es handelt sich um eine Open-Source-Software mit einer aktiven Community, die kontinuierlich daran arbeitet. Ein großer Pluspunkt ist, dass ownCloud den Datenschutzvorschriften, wie der GDPR (General Data Protection Regulation) und der LGPD (Lei Geral de Proteção de Dados), entspricht. Die Software bietet auch die Möglichkeit zur Aktivierung von 2FA (Two-Factor Authentication) und MFA (Multi-Factor Authentication) für zusätzliche Sicherheit. Allerdings könnte ownCloud mehr Informationen über die Funktionalitäten ihrer Software bereitstellen, da ihre Werbung hauptsächlich oberflächlich ist und nicht ins Detail geht.

### Nextcloud
Nextcloud ist ähnlich wie ownCloud, da es ebenfalls als Open-Source-Lösung mit einer aktiven Community entwickelt wird. Nextcloud wirbt mit einem ansprechenden Design und einer Vielzahl von Features. Jedoch liegt uns die Sicherheit besonders am Herzen, und in dieser Hinsicht bietet Nextcloud nicht viel Neues im Vergleich zu ownCloud.

### Pydio
Pydio hebt sich von den vorherigen Lösungen ab, indem es bereits auf den ersten Blick mit seiner Sicherheit, Skalierbarkeit, Open-Source-Natur und den Self-Hosting-Möglichkeiten wirbt. Pydio gibt uns außerdem detailliertere Einblicke in die Funktionsweise ihrer Software. Auf ihrer Webseite konnten wir feststellen, dass Pydio eine breite Palette von Geräten unterstützt, darunter Windows, MacOS, Linux, Android, iPads und iPhones. Die Sicherheit hat für Pydio einen hohen Stellenwert.

### Seafile
Zuletzt haben wir uns Seafile angesehen. Diese Lösung ähnelt Pydio, bietet jedoch zusätzliche Möglichkeiten beim Download. Seafile unterstützt auch ältere Geräte wie Windows 7 und ältere Macs. Interessanterweise kann Seafile auch vollständig über die Kommandozeile unter Linux gesteuert werden, falls dies gewünscht ist. Für Android-Nutzer gibt es die Möglichkeit, Seafile sowohl aus dem Google Play Store als auch von F-Droid herunterzuladen. Selbstverständlich werden auch iPad- und iPhone-Geräte unterstützt.

### Abschließende Gedanken
Bei der Auswahl einer Cloud-Software für Ihren Server ist es wichtig, Ihre Anforderungen an Sicherheit, Funktionalität und Kompatibilität mit verschiedenen Geräten zu berücksichtigen. OwnCloud und Nextcloud sind solide Optionen mit einer aktiven Community, während Pydio mit einem Schwerpunkt auf Sicherheit und Einblick in die Funktionsweise hervorsticht. Seafile bietet zusätzliche Möglichkeiten beim Download und unterstützt eine Vielzahl von Geräten.

| Plattform | ownCloud | Nextcloud | Seafile | Pydio |
|:--------------|:----------------------------|:----------------------------|:----------------------------|:----------------------------|
| Open Source? | Ja | Ja | Ja | Ja |
| Lizenz | AGPLv3 | AGPLv3 | AGPLv3 | AGPLv3 |
| Community | Aktive und engagierte<br>Community | Aktive und engagierte<br>Community | Aktive Community | Aktive Community |
| Verschlüsselung | Server-seitig | Server-seitig | Datei-basiert | Datei-basiert |
