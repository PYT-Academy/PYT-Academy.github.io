---
title: PYT-Academy Self hosted Server Projekt
date: 2023-07-18 12:00:00 -0400
last_modified_at: 2023-08-09 14:00:00 -0400
categories: [Projekte, Server]
tags: [open-source, Self-hosted, Server, Projekt, Cloud, Verein, Cryptomator, Tutorial]
author: david
pin: true
image:
  path: /assets/img/sergius/mac-mini.jpg)
  lqip:
  alt: Profilbild
---

## Update 09.08.2023

### Installation und Einrichtung von OPNsense

- das Immage AMD64 in der VGA Version runderladen und mit Rufus Brennen
- den Rechner von USB Booten, das system startet als Live-System. Nichts machen bis der Anmeldebilschirm erscheint
- Als User: install und Passwort: opnsense eingeben
- Es öffnet sich ein Installations-Assisten. Das einzige was ich ändere ist die Tastatur auf Deutsch und das Dateisystem auf "ZFS". Vergebe ein neues Root Passwort und lasse den Installationsmanager durchlaufen. Bestätige dass die Installation und das Formatieren der Festplatte. Der Installationsmanager startet den Rechner neu und dann geht es im Lokalen Netzwerk weiter
- im Browser die Lokale IP-Adresse eingeben, standard ist 192.168.1.1/24
- es öffnet sich die web-Oberfläche von OPNsense
- als erstes starte ich System-Assistent die Allgemeine Konfiguration und konfiguriere den LAN und WAN Port. Für den WAN-Port werden die Zugansdaten vom Provider benötigt. Ich stelle als Prinären DNS 1.1.1.1 von Cloudflair und als Secundären DNS 8.8.8.8 von Google ein, gebe die PPPoE Zugansdaten ein. Thats it!

Diese Anleitung habe ich benutzt:
{% include embed/youtube.html id='mFEib0zQWg' %}

Alles weitere sind erstmal grundeinstellungen. Das ändern der Schnittstellen kann schwierigkeiten verursachen. Bzw. kommt man an die web-Oberfläche nicht mehr ran und muss über die Konsole die Schnittstellen neu konfigurieren.

Ansonsten ist die Installation und Ersteinrichtung sehr simple. Die Grundeinstellungen sind Solide. Ich nutze die USB zu Ethernet Adapter die mit 100Mbits als Flaschenhals gelten. Kabel und Teile sind bestellt und sobald alles da ist geht es an den Server.

Hallo Team,
Lasst uns an den Aufbaudiagramm arbeiten. Hier der Chatverlauf für weiterführende Informationen

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
Wir haben mit der Router-Installation begonnen. Wir haben ein eigenes WLAN-Netzwerk eingerichtet, das vom bestehenden Router getrennt ist, um eventuellen Problemen vorzubeugen. So konnten wir den Router mit unseren Zugangsdaten problemlos konfigurieren, ohne unser Hauptnetzwerk zu beeinträchtigen. Falls irgendetwas schiefgeht, können wir einfach die Router umstecken.

Zusätzlich haben wir mit unserem Internetanbieter gesprochen und ein Upgrade unserer Leitung auf 300Mbits erhalten. Das ist eine erhebliche Verbesserung gegenüber den bisherigen 100 Up- und Downstream. Momentan verhandeln wir auch noch eine feste IP-Adresse und der Server wird auch bald zum Laufen gebracht.

Für die Router-Konfiguration haben wir uns für den Mac mini entschieden, auf dem wir bereits eine Anleitung für unseren Blog vorbereitet haben. Jetzt warten wir nur noch auf unsere Zugangsdaten, um die Konfiguration abzuschließen. Als Nächstes werden wir den Server auf den zweiten Mac mini installieren.

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

## Cryptomator, verschlüsselung auf dem Client

> Cryptomator! Pro-Tipp von Sergius
{: .prompt-tip }

Cryptomator ist eine bemerkenswerte Lösung, wenn es um die Sicherheit und den Schutz der eigenen Cloud-Daten geht. Im Gegensatz zu allen anderen Cloud-Speicher-Softwarelösungen, fungiert Cryptomator nicht als eigene Cloud-Software, sondern als zusätzliche Sicherheitsschicht für Ihre vorhandenen Cloud-Dienste. Es ist ein Open-Source-Tool, das clientseitige Verschlüsselung für Ihre Dateien bietet, bevor sie in die Cloud hochgeladen werden. Dadurch wird sichergestellt, dass niemand außer Ihnen (nicht einmal Ihr Cloud-Anbieter) auf Ihre sensiblen Daten zugreifen kann.

### Funkionsweise

Cryptomator erstellt einen virtuellen Laufwerksordner auf Ihrem System, in dem Sie Ihre Dateien speichern können. Wenn Sie eine Datei in diesen Ordner verschieben, wird sie automatisch und transparent verschlüsselt und dann in Ihren Cloud-Ordner hochgeladen. Die Verschlüsselung erfolgt nach dem AES-Standard, und der Schlüssel bleibt immer auf Ihrem Gerät, sodass Sie die volle Kontrolle über Ihre Daten haben.

### Einrichtung

- Laden Sie die Cryptomator-Software von der offiziellen Webseite herunter und installieren Sie sie auf Ihrem System.

- Nach der Installation starten Sie Cryptomator und klicken auf das Plus-Symbol, um einen neuen Tresor zu erstellen.

- Wählen Sie den Ort Ihres Cloud-Ordners aus, in dem Sie den Tresor speichern möchten. 

Tipp: Instaliere dir die Desktop-Anwendung deines Cloud-Anbieters {: .prompt-tip }

- Geben Sie einen Namen für den Tresor ein und erstellen Sie ein sicheres Passwort. Dieses Passwort wird verwendet, um Ihre Dateien zu verschlüsseln und zu entschlüsseln, also stellen Sie sicher, dass Sie es sicher aufbewahren.

- Sobald der Tresor erstellt ist, können Sie ihn durch Eingabe Ihres Passworts entsperren und wie ein normales Laufwerk auf Ihrem System verwenden. Alle Dateien, die Sie in diesen Ordner verschieben, werden automatisch verschlüsselt und in den Cloud-Ordner hochgeladen.

> Cryptomator ist eine effektive Lösung, um Ihre Daten in jeder Cloud sicher aufzubewahren. Es ist kompatibel mit verschiedenen Betriebssystemen wie Windows, MacOS und Linux sowie mobilen Plattformen wie Android und iOS. Es ist wichtig zu bedenken, dass während Cryptomator eine zusätzliche Schicht der Sicherheit bietet, es immer noch wichtig ist, sichere Praktiken für den Datenschutz zu befolgen und Ihre Passwörter sicher zu speichern.

## Crowdsack - Open Source Sicherheitstool für euren Server

Wir möchten euch zudem ein fantastisches Open-Source-Sicherheitstool namens "Crowdsack" vorstellen. Mit Crowdsack wird es einfacher, euren Webserver oder auch andere komplexe Systeme abzusichern. Egal ob es sich um WordPress, eine Firewall oder verschiedene interne Systeme eures Unternehmens handelt, Crowdsack bietet euch einen Echtzeitschutz gegen aggressive IPs und das vollkommen kostenlos.

Sicherheit sollte immer eine Priorität sein, vor allem wenn ihr euren Server im öffentlichen Internet betreibt. In wenigen Minuten könnt ihr mit hunderten Brute-Force-Angriffen rechnen, die von Bots aus der Ferne gestartet werden. Daher ist es wichtig, dass ihr eure Website oder Anwendung gut absichert.

Crowdsack analysiert eure Server-Logs in Echtzeit und identifiziert aggressive IPs. Es hilft euch dabei, diese IP-Adressen zu blockieren, sodass sie keinen Zugriff mehr auf euren Server erhalten. Die Regeln, die dabei erstellt werden, basieren auf der Community und werden ständig aktualisiert. Das bedeutet, dass, wenn ihr eine bösartige IP-Adresse blockiert, auch andere Benutzer von Crowdsack von dieser Information profitieren können.

Die Installation von Crowdsack auf eurem Webserver ist denkbar einfach. Ihr könnt den Quellcode von der Crowdsack-Website herunterladen und die Installationsanleitung befolgen. Es gibt auch kostenpflichtige Tarife, aber die meisten Funktionen sind in der kostenlosen Version verfügbar, was sie zu einer großartigen Option für viele Benutzer macht.

Mit Crowdsack könnt ihr eure Server-Sicherheit auf ein neues Level heben. Es bietet Schutz vor Brute-Force-Angriffen, verfügt über eine Vielzahl von Szenarien und Blocklisten, und die Threat Intelligence-Funktion ermöglicht es euch, bösartige IPs zu identifizieren und zu blockieren.

Insgesamt sind wir sehr beeindruckt von Crowdsack und werden es weiterhin auf unseren Servern einsetzen, um unsere Webanwendungen und Daten zu schützen.

{% include embed/youtube.html id='REiTqc_WV9w' %}