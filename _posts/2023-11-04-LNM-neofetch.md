---
title: Linux nach Maß∶ Neofetch
date: 2023-11-04 11:00:00 -0400
last_modified_at: 2023-11-04 11:00:00 -0400
categories: [LNM, linux]
tags: [Neofetch, Bearbeiten, Logo, ASCII, Terminal, Bash, Zsh]
author: david
comments: true
image:
  path: /assets/img/LNM_neofetch.png
---

# Neofetch

## Was ist neofetch

Neofetch ist ein Befehlszeilenprogramm, das dazu dient, systemrelevante Informationen und Informationen zur Systemkonfiguration anzuzeigen. Du kannst es verwenden, um schnell herauszufinden, welche Betriebssystemversion du verwendest und welche Hardwarekomponenten in deinem System installiert sind. Neofetch ist auch nützlich, wenn du deine Systemkonfiguration mit anderen teilen möchtest.

# Bearbeiten

## Wo sind die Dateien?

Um neofetch anzupassen, musst du einige Dateien bearbeiten. Die Hauptdatei, die du bearbeiten wirst, ist die Konfigurationsdatei. Du findest sie normalerweise unter dem Pfad `~/.config/neofetch/config.conf`.

## Was ist da zu tun?

In der Konfigurationsdatei `config.conf` kannst du verschiedene Einstellungen vornehmen, um das Aussehen und Verhalten von neofetch anzupassen. Hier sind einige der Konfigurationsoptionen, die du in der Datei bearbeiten kannst:

## print_info

Die print_info Konfiguration ermöglicht es dir, die einzelnen Ausgaben von neofetch anzupassen. Du kannst Zeilen mit einem `#` auskommentieren, um bestimmte Informationen zu deaktivieren oder sie aktivieren, indem du das `#` entfernst.

## Ausgabe konfigurieren

Die nachfolgenden Zeilen erläutern die individuellen Ausgaben, wie beispielsweise das **Betriebssystem** oder den **Kernel**. Jede dieser Ausgaben ist kommentiert und mit Beispielen versehen, die ihre genaue Bedeutung verdeutlichen.

# Logo

Die Konfigurationsoptionen `ascii_distro` und `ascii_colors` ermöglichen die Anpassung des ASCII-Art-Logos und der Farben in neofetch. Hier ist, wie du diese Optionen findest und bearbeitest:

**ascii_distro**: Diese Konfigurationsoption erlaubt es dir, das ASCII-Art-Logo für deine Distribution oder dein Betriebssystem anzupassen. Es gibt vordefinierte Logos für verschiedene Betriebssysteme. 
Ändere den Wert von `ascii_distro` auf den Dateinamen des gewünschten ASCII-Art-Logos. Zum Beispiel, wenn du das Debian-Logo verwenden möchtest, ändere `ascii_distro` zu:

```ascii_distro="Debian"```

Wenn du dein eigenes Bild in neofetch einfügen möchtest folge diesen Schritten:

1. **Erstelle dein ASCII-Art-Logo:** Beginne damit, das Bild deiner Wahl in ASCII-Art umzuwandeln. Es gibt verschiedene Online-Konverter und ASCII-Art-Generatoren, die dir dabei helfen können. Achte darauf, dass die Größe und der Stil des Logos deinen Vorstellungen entsprechen.

2. **Speichere das ASCII-Art-Logo:** Speichere das generierte ASCII-Art-Logo in einer Textdatei mit einer geeigneten Dateiendung wie .txt. Notiere dir den Dateipfad, unter dem du die Datei gespeichert hast.

3. Konfiguriere `image_source` in der `config.conf`-Datei:

```image_source="/Pfad/zur/deiner/ascii_art.txt"```

Zusätzlich kannst du neofetch auch direkt mit dem gewünschten ASCII-Art-Logo aufrufen, indem du den Befehl `neofetch --source Bild` verwendest, wobei "Bild" der Pfad zu deiner ASCII-Art-Datei ist. Zum Beispiel:

```neofetch --source /Pfad/zur/deiner/ascii_art.txt```

Oder du kannst spezifische ASCII-Art-Logos für bestimmte Betriebssysteme auswählen, indem du den Befehl `neofetch --ascii_distro Distro` verwendest, wobei "Distro" für den Namen deines Betriebssystems steht. Zum Beispiel:

```neofetch --ascii_distro debian```

Das ermöglicht es dir, neofetch temporär mit spezifischen Logo-Quellen oder Betriebssystem-Logos anzuzeigen, ohne die `config.conf`-Datei zu bearbeiten.

**ascii_colors**: Diese Konfigurationsoption ermöglicht es dir, die Farben für das ASCII-Art-Logo in neofetch anzupassen. Du kannst die Textfarbe und den Hintergrund des Logos ändern.
Du kannst die HEX-Farbcodes nach deinen Vorlieben ändern. Zum Beispiel:

```ascii_colors=(27 33)```

Eine liste der Farben findest du hier:

![Test Diagram](/assets/img/color-codes.png)

# Neofetch im Terminal

## Wie öffnet sich neofetch im Terminal automatisch?

Wenn du neofetch jedes Mal automatisch im Terminal sehen möchtest, wenn du ein neues Terminal-Fenster öffnest, kannst du dies erreichen, indem du es in deine Shell-Startdatei integrierst. Hier sind die Schritte für einige gängige Shells:

### Bash:

1. Öffne deine `~/.bashrc` Datei mit einem Texteditor. Ich nutze persönlich VIM für diese Aufgabe, aber du stehst frei, den Texteditor deiner Wahl zu verwenden.

```vim ~/.bashrc```

2. Füge am Ende der Datei die folgende Zeile hinzu:

```neofetch```

3. Speichere die Datei und schließe den Texteditor.
4. Starte ein neues Terminal, und neofetch wird automatisch angezeigt.

### Zsh

1. Öffne deine `~/.zshrc` Datei mit einem Texteditor. Ich nutze persönlich VIM für diese Aufgabe, aber du stehst frei, den Texteditor deiner Wahl zu verwenden.

```vim ~/.zshrc```

2. Füge am Ende der Datei die folgende Zeile hinzu:

```neofetch```

3. Speichere die Datei und schließe den Texteditor.
4. Starte ein neues Terminal, und neofetch wird automatisch angezeigt.

### Für andere Shells, wie Fish, passe die entsprechende Startdatei an.

Jetzt wird neofetch jedes Mal beim Öffnen eines neuen Terminal-Fensters angezeigt und zeigt Informationen über dein System an.