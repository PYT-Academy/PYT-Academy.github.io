---
title: Gaming unter Linux, Herausforderungen und Möglichkeiten
date: 2023-08-19 11:00:00 -0400
last_modified_at: 2023-08-19 11:00:00 -0400
categories: [Technik, Linux, Gaming]
tags: [Linux, Gaming, Proton, Wine, Valve, Steam, Minecraft, MultiMC, Lutris, Bottles, Battle.net, League of Legends, Anticheat-Systeme, Valorant, Roblox]
author: david
image:
  path: /assets/img/gaming-banner.png
---

# Gaming unter Linux: Herausforderungen und Möglichkeiten

Linux ist bekannt für seine Vielseitigkeit und Anpassungsfähigkeit in der Welt der Technologie. Neben seiner Verwendung in Serverumgebungen und als Betriebssystem für Entwickler hat Linux in den letzten Jahren auch große Fortschritte im Bereich Gaming gemacht. In diesem Artikel werfen wir einen Blick auf die Herausforderungen und Möglichkeiten des Gamings unter Linux.

## Die Herausforderungen

Das Spielen unter Linux war lange Zeit mit einigen Herausforderungen verbunden. Eine der größten war die begrenzte Verfügbarkeit von Spielen, die speziell für Linux entwickelt wurden. Viele Spiele wurden ausschließlich für Windows veröffentlicht, was Linux-Gamer oft frustrierte.

## Die Möglichkeiten

In den letzten Jahren hat sich die Situation jedoch drastisch verändert. Dank Projekten wie [Proton](https://www.protondb.com/) und [Wine](https://www.winehq.org/) können viele Windows-Spiele jetzt auch unter Linux gespielt werden. Diese Kompatibilitätsschichten haben die Tür für eine breitere Palette von Spielen geöffnet, die zuvor auf Linux nicht verfügbar waren.

## Proton und Wine: Spielen mit Kompatibilität

Ein Meilenstein in der Welt des Linux-Gamings war die Einführung von **Proton**, einer von Valve entwickelten Technologie. Proton baut auf der **Wine**-Kompatibilitätsschicht auf und ermöglicht es, eine breite Palette von Windows-Spielen nahtlos unter Linux zu spielen. Es nutzt verschiedene Techniken, um Spiele zu optimieren und die Kompatibilität zu verbessern.

**Wine** hingegen ist eine Open Source-Software, die es ermöglicht, Windows-Anwendungen und -Spiele auf Linux-Systemen auszuführen. Wine arbeitet daran, die Windows-APIs nachzubilden, um eine Umgebung zu schaffen, in der Windows-Software unter Linux läuft.

## Valve und Steam

![Desktop View](/assets/img/valve-logo.png){: width="256" height="256" .left}

**Valve**, das Unternehmen hinter der beliebten Spieleplattform **Steam**, hat einen großen Beitrag zur Förderung des Linux-Gamings geleistet. Neben der Einführung von Proton hat Valve auch viele seiner eigenen Spiele für Linux veröffentlicht. Dies hat dazu beigetragen, das Spieleangebot für Linux erheblich zu erweitern.

**Steam** ist eine der größten digitalen Vertriebsplattformen für Spiele. Unter Linux bietet Steam eine breite Auswahl an Spielen, die direkt auf Linux ausgeführt werden können. Dank Proton können aber auch viele der Windows-Spiele, die auf Steam erhältlich sind, unter Linux gespielt werden.

### Einrichten von Steam unter Linux

![Desktop View](/assets/img/steam-logo.png){: width="256" height="256" .left}

Die Einrichtung von Steam unter Linux ist ein einfacher Prozess:

1. **Installation von Steam**: Öffne ein Terminal und verwende die Paketverwaltung deiner Linux-Distribution, um Steam zu installieren.

2. **Anmeldung bei Steam**: Starte Steam nach der Installation und melde dich mit deinem Steam-Konto an oder erstelle ein neues Konto.

3. **Spiele installieren**: Du kannst Spiele durchsuchen, installieren, die speziell für Linux verfügbar sind.

4. **Proton einrichten**:
    - Navigiere zu den Einstellungen: Klicke oben links auf "Steam" und wähle dann "Einstellungen" aus dem Dropdown-Menü.
    - Wechsle zur Steam Play-Option: In den Einstellungen öffnet sich ein neues Fenster. Klicke auf den Tab "Kompatibilität" in der linken Seitenleiste.
    - Aktiviere Steam Play für alle Titel: Markiere das Kästchen neben "Steam Play für unterstützte Titel Aktivieren" und "Steam Play für alle anderen Titel aktivieren".
    - Wähle Proton-Version: Stelle sicher, dass unter "Führen Sie andere Titel mit" die neueste Proton-Version aus dem Dropdown-Menü ausgewählt ist.
    - Speichere die Einstellungen: Klicke auf "OK", um die Einstellungen zu speichern und das Fenster zu schließen.

5. **Spielen von Windows-Spielen unter Linux**:
    - Installiere Windows-Spiele: Suche im Steam Store nach Windows-Spielen, die du unter Linux spielen möchtest, und installiere sie wie gewohnt.
    - Starte das Spiel: Nach der Installation kannst du das Spiel aus deiner Steam-Bibliothek starten. Steam wird automatisch Proton verwenden, um das Spiel unter Linux auszuführen.

6. **Spielen unter Linux**: Nach der Installation kannst du Spiele unter Linux direkt aus der Steam-Bibliothek starten und spielen.

Mit diesen Schritten hast du erfolgreich Proton in Steam eingerichtet und bist bereit, Windows-Spiele unter Linux zu spielen. Beachte, dass nicht alle Spiele perfekt unter Proton laufen, aber viele Spiele können problemlos gespielt werden, insbesondere mit den neuesten Proton-Versionen.

## Minecraft

![Desktop View](/assets/img/minecraft-logo.png){: width="256" height="256" .left}

Minecraft, ein beliebtes Sandbox-Spiel, ist ein herausragendes Beispiel dafür, wie Spiele plattformübergreifend sein können. Egal, ob du ein Linux-, Windows- oder macOS-Benutzer bist, Minecraft ist auf praktisch jedem Betriebssystem verfügbar. Dies liegt größtenteils daran, dass Minecraft in Java geschrieben ist, was es ermöglicht, eine Version des Spiels zu erstellen, die auf verschiedenen Plattformen läuft.

Die Java-Edition von Minecraft bietet eine konsistente Spielerfahrung, unabhängig vom Betriebssystem, auf dem es gespielt wird. Dies hat dazu beigetragen, dass Minecraft zu einem der am weitesten verbreiteten und geliebten Spiele weltweit wurde.

### MultiMC: Ein empfohlener Launcher für Minecraft unter Linux

Wenn es um das Verwalten von Minecraft-Installationen und Mods unter Linux geht, ist der **MultiMC Launcher** eine ausgezeichnete Wahl. MultiMC ist ein Open Source Launcher, der entwickelt wurde, um das Verwalten von verschiedenen Minecraft-Versionen und Modifikationen zu erleichtern. Hier sind einige Gründe, warum MultiMC empfohlen wird:

- **Leichte Verwaltung**: MultiMC ermöglicht es dir, verschiedene Versionen von Minecraft zu installieren und zwischen ihnen zu wechseln, ohne Konflikte zu verursachen.

- **Mod-Unterstützung**: Du kannst Mods einfach zu deinen Minecraft-Versionen hinzufügen und verwalten. MultiMC erleichtert das Organisieren und Aktivieren von Mods.

- **Unabhängige Versionen**: Jede Minecraft-Version in MultiMC ist unabhängig voneinander. Das bedeutet, dass Änderungen in einer Version keine Auswirkungen auf andere haben.

- **Backup und Wiederherstellung**: MultiMC ermöglicht es dir, Backups von deinen Minecraft-Versionen zu erstellen und sie bei Bedarf wiederherzustellen.

Die Verwendung von MultiMC kann deine Minecraft-Erfahrung unter Linux erheblich verbessern, indem es dir mehr Kontrolle über deine Installationen und Mods gibt.

## Lutris: Eine Plattform für Spieleverwaltung unter Linux

**Lutris** ist eine Open Source-Plattform, die es ermöglicht, Spiele unter Linux zu installieren, zu organisieren und auszuführen. Es bietet eine benutzerfreundliche Schnittstelle, die es dir erleichtert, Spiele von verschiedenen Quellen zu installieren und zu spielen, unabhängig davon, ob sie für Linux, Windows oder andere Plattformen entwickelt wurden.

### Vorteile von Lutris:

1. **Spielintegration**: Lutris bietet eine wachsende Liste von Spielen, die direkt über die Plattform installiert und verwaltet werden können. Dabei handelt es sich sowohl um Linux-spezifische als auch um Windows-Spiele, die unter Wine oder Proton laufen.

2. **Automatische Konfiguration**: Lutris erleichtert die Einrichtung von Spielen, die Wine oder Proton verwenden. Es konfiguriert automatisch die notwendigen Einstellungen, um die bestmögliche Kompatibilität zu gewährleisten.

3. **Bibliotheksverwaltung**: Du kannst deine Spielesammlung in Lutris organisieren, Spiele starten, Aktualisierungen überwachen und Patches anwenden.

4. **Community**: Lutris bietet eine aktive Community, in der Nutzer Erfahrungen, Tipps und Ratschläge zum Spielen unter Linux austauschen können.

### Lutris verwenden:

1. **Installation von Lutris**: Abhängig von deiner Linux-Distribution kannst du Lutris aus den Paketquellen installieren.

2. **Spiele installieren**: Nach der Installation öffne Lutris und suche nach Spielen in der Lutris-Datenbank. Du kannst auch eigene Spiele hinzufügen.

3. **Einstellungen anpassen**: Für Windows-Spiele kannst du Proton oder Wine verwenden. Lutris bietet Optionen zur Konfiguration dieser Laufzeitumgebungen, um die bestmögliche Kompatibilität zu erreichen.

4. **Spiele starten**: Sobald Spiele installiert sind, kannst du sie einfach über die Lutris-Oberfläche starten.

Lutris ist eine großartige Ergänzung für Linux-Gamer, die eine zentrale Anlaufstelle für die Verwaltung ihrer Spiele suchen, unabhängig von der Plattform, für die sie entwickelt wurden. Es erleichtert den Zugang zu einer breiten Palette von Spielen und verbessert die Spielerfahrung unter Linux erheblich.

## Bottles: Eine Lösung für Windows-Programme unter Linux

**Bottles** ist ein Frontend für **Wine**, das dazu dient, Windows-Programme auf Linux-Systemen auszuführen. Es bietet eine benutzerfreundliche Oberfläche, um Wine-Instanzen zu erstellen und Programme darin zu installieren. Hier ist eine Anleitung zur Einrichtung von Bottles und zur Ausführung von Windows Programmen:

1. **Installation von Bottles**: Öffne ein Terminal und befolge die Anweisungen, um Bottles zu installieren. Abhängig von deiner Linux-Distribution kann der Befehl variieren.
   
2. **Bottles starten**: Suche nach "Bottles" in deinem Anwendungsmenü und starte die Anwendung.

3. **Erstellen einer Bottle**: Klicke auf "New Bottle erstellen" und wähle den Namen für deine neue Wine-Instanz aus. Du kannst auch die Wine-Version auswählen, die für diese Instanz verwendet werden soll.

4. **Installation von Windows Programmen**: Nachdem die Bottle erstellt wurde, klicke auf "Programm installieren" und wähle die Datei aus, die du ausführen möchtest. Befolge die Anweisungen des Installationsprogramms.

Hier ist die offizielle Liste der von Wine unterstützten Programme: [WineHQ-Database](https://appdb.winehq.org/)

### Video
{% include embed/youtube.html id='o2HUNRPUDkU' %}

### Battle.net und dessen Spiele

![Desktop View](/assets/img/battle.net-logo.png){: width="256" height="256" .left}

1. **Battle.net Launcher**:
- Erstelle eine neue Bottle für den Battle.net Launcher.
- Installiere den Launcher, indem du die Installer Datei auswählst.
- Nach der Installation öffne den Launcher innerhalb der Bottle.

2. **Battle.net Spiele**:
- Installiere Overwatch 2, Hearthstone oder andere Battle.net Spiele über den Battle.net Launcher in der Bottle.
- Danach kannst du die spiele starten und in der Wine basierten Umgebung spielen.

### League of Legends

![Desktop View](/assets/img/league-of-legends-logo.png){: width="256" height="256" .left}

1. **League of Legends**:
- Erstelle eine neue Bottle für League of Legends.
- Lade den League of Legends Installer von der offiziellen Website herunter.
- Installiere das Spiel in der Bottle, indem du den heruntergeladenen Installer auswählst.
- Folge den Anweisungen, um das Spiel zu konfigurieren.

Für detailliertere Anweisungen zur Installation von League of Legends unter Bottles, schau dir von [diesem Leitfaden](https://www.linuxfordevices.com/tutorials/linux/install-league-of-legends) Schritte 1-3 an.

## Spiele, die aufgrund von Anticheat-Systemen nicht unter Linux laufen

Während Linux eine zunehmend attraktive Plattform für Gaming geworden ist, gibt es immer noch einige Spiele, die nicht direkt auf Linux laufen, insbesondere aufgrund von Client-seitigen Anticheat-Systemen. Diese Systeme sind darauf ausgelegt, das Spielen fair zu gestalten, indem sie das Cheaten verhindern. Leider sind sie oft nicht mit Linux kompatibel. Hier sind zwei Beispiele:

### Valorant

![Desktop View](/assets/img/valorant-logo.png){: width="256" height="256" .left}

**Valorant** ist ein beliebter taktischer Shooter von Riot Games. Das Spiel verwendet den Vanguard-Anticheat-Systemtreiber, der tief in das Betriebssystem integriert ist. Leider ist Vanguard derzeit nicht mit Linux kompatibel, was bedeutet, dass das Spielen von Valorant auf einem Linux-System nicht möglich ist, ohne spezielle Umstände oder Virtualisierungslösungen.

### Roblox

![Desktop View](/assets/img/roblox-logo.png){: width="256" height="256" .left}

**Roblox** ist eine Gaming-Plattform, auf der Nutzer ihre eigenen Spiele erstellen und spielen können. Auch hier gibt es eine Einschränkung für Linux-Nutzer aufgrund von Anticheat-Systemen. Das Spiel verwendet einen Client-seitigen Anticheat, der unter Linux nicht unterstützt wird. Das bedeutet, dass das Spielen von Roblox auf einem Linux-System ebenfalls kompliziert sein kann.

Es ist wichtig, sich bewusst zu sein, dass die fehlende Unterstützung für Linux in diesen Fällen nicht immer in der Kontrolle der Entwickler liegt, sondern oft auf den Anforderungen von Anticheat-Systemen basiert.

