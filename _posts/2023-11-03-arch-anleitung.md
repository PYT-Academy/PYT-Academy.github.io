---
title: Arch-Linux, mein Setup 
author: sergius
date: 2023-11-03 11:33:00 +0800 #Datumformat entscheidet über die Sortierreinfolge.
categories: [Linux, Arch-Setup Sergius ] #Kategorieauswahl laut Webseite bestimmen.
tags: [Anfänger, Anleitung, Arch, Community, ] #mindestens 3 Tags aus jeweils einzelnen Wörtern verfassen
pin: true #ist zum Anpinnen des Artikels auf den Oberen Rängen. mehrere Angepinnte Artikel werden nach Datum sortiert
math: true #nur für Matematische Formeln im Artikel benötigt
mermaid: true #nur für Mermaid diagramme benötigt
image:
  path: /assets/img/blogpost-231103/Arch-kiss.png
  alt: Arch Logo mit KISS-Philosophie (Keep it simple and Stupid)
---

## Begrüßung

Nach monatelangem Distro-Hopping und dem desaster der Desktopmanager bin ich jetzt zu einer Entscheidung gekommen und möchte sie dir vorstellen. Ich benutze 4 Systeme. Zwei sind für die Arbeit das dritte ist für's Studium und das Vierte ist Privat. Hier soll es um das Studium Setup gehen welches später mein Privates Setup erseten wird. 

### warum Arch?

- ist primär eine Persönliche Entscheidung. Ich mag das System hauptsächlich wegen der dahinterstehenden Philosophie und der Community. 
- Wer lesen kann ist ist hier klar im Vorteil. Das meiste ist bereits Dokumentiert, mann muss nur wissen wo ind wie man darauf zugreift.
- Arch bietet ein Minimales Grundsystem und überlässt dem Nutzer sämtliche Entscheidungen über die weitere Konfiguration. Arch zwingt dich dazu sich mit deinem System zu beschäftigen. Das gilt auch für Arch basierende Distributionen (ausnahme bidet Manjaro, von der Disro habe ich mich bereits Distanziert) Aber mein Berufliches Linux System ist EndevourOS und diese Distribution verzichtet bewusst auf Grafische Packetmanager wie es auch die Arch-Wiki empfielt.
- Ich beziehe mich auch oft auch die [Deutschsprachige Arch-Wiki](https://wiki.archlinux.de/title/Hauptseite){:target="_blank"} und deren Unterseiten. Falls es keine Deutschsprachige Anleitung gibt geht es mit der [Englischsprachigen Arch-Wiki](https://wiki.archlinux.org/){:target="_blank"} weiter. Und zu guterletzt geht's weiter ins [Arch-Forum](https://bbs.archlinux.org/){:target="_blank"}. Achtung: wer im Forum Fragen stellt die in der Arch-Wiki beschrieben sind, erntet unter umständen Hohn und Spott. Bitte benutze das Forum ausschließlich wenn du in der Arch-Wiki nicht weiterkommst und verweise auch auf die Entsprechenden Artikel damit sich die Forumleute das genau ansehen können...

### Hardware

hier möchte ich kurz auf die Hardware von meinem Studium-System sprechen. Ich präferiere die ThinkPad Reihe aus 2011. Insbesondere die ThinkPad Modelle [X220](https://thinkwiki.de/X220){:target="_blank"}, [W520](https://thinkwiki.de/W520){:target="_blank"} und das [T420](https://thinkwiki.de/T420){:target="_blank"}. Die Anderen modelle aus der Rheihe sind möglich, jedoch obsolet. es werden die Displaydiagonalen 12,5", 14" und 15" abgedeckt und jedes Modell steht für seinen Zweck top ausgestattet und solide da. In der [Deutschsprachigen ThinkPad-Wiki](https://thinkwiki.de/Hauptseite){:target="_blank"} findest du alle informationen.

Natürlich gehen auch andere Modelle und neuere eigene Hardware. Fühl dich frei zu nutzen was du willst. Ich beziehe meine Anleitungen ausschließlich auf diese Geräte und Arch-Linux basierte Systeme.

> Wichtige Begriffe stelle ich in solchen `Promts` dar. In diesem Fall möcht ich den Begriff `Propriätär` ansprechen. Wenn du mit Linux oder allgemein mit Open-Source oder dich mit dem [GNU-Project](https://www.gnu.org/philosophy/philosophy.html){:target="_blank"} auseinadersetzen willst. Dann solltest du den begriff `Proprietär` unbeingt verstehen und wissen welche Software und Hardware Proprietär ist. 
{: .prompt-warning }

### bevor es losgeht

- nutze die `Kommentarfunktion` und schreibe mir bei unklarheiten oder allgemenen Fragen.
- Kontaktiere mich. 
  - [PYT-Academy Discord Server](https://discord.gg/WxaJcnuXAh){:target="_blank"}
  - [IT-Systemhaus Telegram-Gruppe](https://t.me/IT_Systemhaus){:target="_blank"}
  - Lass ein Like im Kommentarbereich da ;-)

## Vorbereitung für die Arch-Installation

### BIOS oder UEFI

- Du musst verstehen wie dein Rechner Startet. Das ältere System ist `BIOS` (Basic Input/Output System) welches nach und nach durch `UEFI` (Unified Extensible Firmware Interface) ersetzt. Ich gehe von UEFI aus was heutzutage der Standard ist. Die Thinkpads aus 2011 habe bereits alle UEFI. Die Projekte [Coreboot](https://www.coreboot.org/){:target="_blank"} und [Libreboot](https://libreboot.org/){:target="_blank"} lasse ich mal beiseite. 



### Partitionierung. 

- Ist ein Riesiges Themengebiet und wird in der  Der [DE-Arch-Wiki "Einrichtung des Datenträgers"](https://wiki.archlinux.de/title/Anleitung_f%C3%BCr_Einsteiger){:target="_blank"} beschrieben. Der Einfachheit halber benutze ich ein Standard-Layout bestehend aus einer `Boot`, `Root` und `SWAP` Partition. Der Vorteil ist dass die Einrichtung wesentlich einfacher ist und ich kann die SSD von einem Laptop in einen andaren umbauen und mit minimalen einrichtugnen läuft mein eigenes System wieder.


![Desktop View](/assets/img/blogpost-231103/lsblk-devices.png){: width="419" height="162" .w-75 .right}
mit [lsblk](https://wiki.archlinux.de/title/Lsblk){:target="_blank"} kann man sich alle angeschlossenen Blockgeräte, also Festplatten, CD/DVD-Laufwerke und USB-Sticks, anzeigen lassen. `sda`, `sdb`, `scd`, `sr0` stehen für die verschiedenen Blockgeräte. Für den anfang identifizieren wir unsere Installationsfestplatte die als `sda` gekennzeichnet ist.

#### Ausgabe von `lsblk` mit Optionen `-ld` und Argumenten `NAME,FSTYPE,GROUP,MODEL,MODE`

```
lsblk -ld --output NAME,FSTYPE,GROUP,MODEL,MODE
NAME FSTYPE GROUP   MODEL            MODE
sda         disk    WDC WD5000AAKS   brw-rw----
sdb         disk    ST3250410AS      brw-rw----
sdc         disk    STORE N GO       brw-rw----
sr0  udf    optical CD/DVDW SH-S182M brw-rw----
```

### iso auf USB-Schreiben

- Du solltest die Arch-Linux ISO auf einen USB-Stick schreiben können und von diesem anschließend auch Booten [DE-Arch-Wiki "Vorbereitung"](https://wiki.archlinux.de/title/Anleitung_f%C3%BCr_Einsteiger){:target="_blank"}

```Spickzettel
dd bs=4M if=/pfad/archlinux-*-x86_64.iso of=/dev/sdx status=progress oflag=sync
```

### Programiersprache "Bash" (Bourne-Again SHell) im Terminal

[Bash](https://wiki.archlinux.de/title/Bash){:target="_blank"} ist die Standard Shell unter Arch-Linux. Es ist eine Scriptsprache für die Kommunikation mit dem Kernel. Der Grundaubau besteht aus einem `Operator` (oder `Task`) gefolgt von (optionalen) `Option:en` und `Argument:en`. Für den Anfang ist es wichtig zu verstehen dass im Terminal jedes Zeichen eine bedeutung hat (sogar ein Lehrzeichen) und Groß-Kleinschreibung spielt eine wichtige rolle.

### im Arch-Linux Livesystem


