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

- ist primär eine `Persönliche Entscheidung`. Ich mag das System hauptsächlich wegen der dahinterstehenden Philosophie und der Community. 

- `Wer lesen kann ist ist klar im Vorteil`. Das meiste ist bereits Dokumentiert, mann muss nur wissen wo ind wie man darauf zugreift. Die Hier erstellten Links verweisen auf die Entsprechende Webseite und scrallen automatisch zum Abstz um den es geht.

- Arch bietet ein `Minimales Grundsystem` und überlässt dem Nutzer sämtliche Entscheidungen über die weitere Konfiguration und die Grafische Benutzeroberfläche. 

- Arch-Linux und dessen Derivate `zwingen dich dazu sich mit deinem System zu beschäftigen`. Das gilt auch für Arch basierende Distributionen (ausnahme bidet Manjaro, von der Disro habe ich mich bereits Distanziert)

- meine Berufliche Linux-Distribution ist EndevourOS `(EOS)` und diese Distribution verzichtet bewusst auf Grafische Packetmanager und lässt dir bei der Installation deine Desktopumgebung oder sogar einen Windowmanager wählen.

> An dieser stelle möchte ich über den `Orangenen Promt` sprechen. Sobald du den Orangenen Promt siehst kannst du mich unterstützen. In diesem fall geht es um die [UNIX-Philosophie von Mike Gancars](https://de.wikipedia.org/wiki/Unix-Philosophie#Mike_Gancarz:_The_UNIX_Philosophy){:target="_blank"} er hat ein Buch dazu veröffentlicht und ich würde die Kernessenz daraus, gerne in einem Blogartikel zusammenfassen. Wenn du mich unterstützen willst, schicke mir ein Script in dem du die wichtigsten Punkte der UNIX-Philosophy von Mike zusammenfasst.
{: .prompt-warning }

- Ich beziehe mich auch oft auch die [Deutschsprachige Arch-Wiki](https://wiki.archlinux.de/title/Hauptseite){:target="_blank"} und deren Unterseiten. Falls es keine Deutschsprachige Anleitung gibt geht es mit der [Englischsprachigen Arch-Wiki](https://wiki.archlinux.org/){:target="_blank"} weiter. Und zu guterletzt geht's weiter ins [Arch-Forum](https://bbs.archlinux.org/){:target="_blank"}. Achtung: wer im Forum Fragen stellt die in der Arch-Wiki beschrieben sind, erntet unter umständen Hohn und Spott. Bitte benutze das Forum ausschließlich wenn du in der Arch-Wiki nicht weiterkommst und verweise auch auf die Entsprechenden Artikel damit sich die Comunity das genau ansehen können...

### Hardware

hier möchte ich kurz auf die Hardware von meinem Studium-System sprechen. Ich präferiere die ThinkPad Reihe aus 2011. Insbesondere die ThinkPad Modelle [X220](https://thinkwiki.de/X220){:target="_blank"}, [W520](https://thinkwiki.de/W520){:target="_blank"} und das [T420](https://thinkwiki.de/T420){:target="_blank"}. Die Anderen modelle aus der Rheihe sind möglich, jedoch obsolet. es werden die Displaydiagonalen 12,5", 14" und 15" abgedeckt und jedes Modell steht für seinen Zweck top ausgestattet und solide da. In der [Deutschsprachigen ThinkPad-Wiki](https://thinkwiki.de/Hauptseite){:target="_blank"} findest du alle informationen.

Natürlich gehen auch andere Modelle und neuere eigene Hardware. Fühl dich frei zu nutzen was du willst. Ich beziehe meine Anleitungen ausschließlich auf diese Geräte und Arch-Linux basierte Systeme.

> wichtige Begriffe stelle ich in `grünen` Tip-Promts dar. In diesem Fall möchte ich den Begriff `Propriätär` ansprechen. Wenn du mit Linux oder allgemein mit Open-Source oder dich mit dem [GNU-Project](https://www.gnu.org/philosophy/philosophy.html){:target="_blank"} auseinadersetzen willst. Dann solltest du den begriff `Proprietär` unbeingt verstehen und wissen welche Software und Hardware Proprietär ist. 
{: .prompt-tip }

### befor es losgeht

- nutze die [Kommentarfunktion](https://pyt-academy.github.io/posts/arch-anleitung/#disqus_thread) und schreibe mir bei unklarheiten oder allgemenen Fragen.
- Kontaktiere mich. 
  - [PYT-Academy Discord Server](https://discord.gg/WxaJcnuXAh){:target="_blank"}
  - [IT-Systemhaus Telegram-Gruppe](https://t.me/IT_Systemhaus){:target="_blank"}
  - Lass ein Like im Kommentarbereich da ;-)

## Vorbereitung für die Arch-Installation

### BIOS oder UEFI

- Du musst verstehen wie dein Rechner Startet. Das ältere System ist `BIOS` (Basic Input/Output System) welches nach und nach durch `UEFI` (Unified Extensible Firmware Interface) ersetzt. Ich gehe von UEFI aus was heutzutage der Standard ist. Die Thinkpads aus 2011 habe bereits alle UEFI. Die Projekte [Coreboot](https://www.coreboot.org/){:target="_blank"} und [Libreboot](https://libreboot.org/){:target="_blank"} lasse ich mal beiseite. 



### Partitionierung. 

- Ist ein Riesiges Themengebiet und wird in der  Der [DE-Arch-Wiki "Einrichtung des Datenträgers"](https://wiki.archlinux.de/title/Anleitung_f%C3%BCr_Einsteiger#Einrichtung_des_Datentr.C3.A4gers){:target="_blank"} beschrieben. Der Einfachheit halber benutze ich ein Standard-Layout bestehend aus einer `Boot`, `Root` und `SWAP` Partition. Der Vorteil ist dass die Einrichtung wesentlich einfacher ist und ich kann die SSD von einem Laptop in einen andaren umbauen und mit minimalen einrichtugnen läuft mein eigenes System wieder.



mit [lsblk](https://wiki.archlinux.de/title/Lsblk){:target="_blank"} kann man sich alle angeschlossenen Blockgeräte, also Festplatten, CD/DVD-Laufwerke und USB-Sticks, anzeigen lassen. `sda`, `sdb`, `scd`, `sr0` stehen für die verschiedenen Blockgeräte. Für den anfang identifizieren wir unsere Installationsfestplatte die als `sda` gekennzeichnet ist.

#### Ausgabe von `lsblk` mit Optionen `-ld` und Argumenten `--output NAME,FSTYPE,GROUP,MODEL,MODE`

```bash
lsblk -ld --output NAME,FSTYPE,GROUP,MODEL,MODE
```

```
NAME FSTYPE GROUP   MODEL            MODE
sda         disk    WDC WD5000AAKS   brw-rw----
sdb         disk    ST3250410AS      brw-rw----
sdc         disk    STORE N GO       brw-rw----
sr0  udf    optical CD/DVDW SH-S182M brw-rw----
```

### iso auf USB-Stick schreiben

Du solltest die Arch-Linux ISO auf einen USB-Stick schreiben können und von diesem anschließend auch Booten [DE-Arch-Wiki "Vorbereitung"](https://wiki.archlinux.de/title/Anleitung_f%C3%BCr_Einsteiger#Vorbereitung){:target="_blank"}

#### Spickzettel
```bash
dd bs=4M if=/pfad/archlinux-*-x86_64.iso of=/dev/sdx status=progress oflag=sync
```

### Programiersprache "Bash" (Bourne-Again SHell) im Terminal

[Bash](https://wiki.archlinux.de/title/Bash){:target="_blank"} ist die Standard Shell unter Arch-Linux. Es ist eine Scriptsprache für die Kommunikation mit dem Kernel. Der Grundaubau besteht aus einem `Operator` (oder `Task`) gefolgt von (optionalen) `Option:en` und `Argument:en`. Für den Anfang ist es wichtig zu verstehen dass im Terminal jedes Zeichen eine bedeutung hat (sogar ein Lehrzeichen) und Groß-Kleinschreibung spielt eine wichtige rolle.

### im Arch-Linux Livesystem

![Desktop View](/assets/img/blogpost-231103/Arch-Linux-Start.png){: width="290" height="117" .w-25 .right}
Das Bootmenu der Live-ISO gibt dir hinweise auf dein System achte auf `UEFI` in der obersten Zeile.

## Arch Linux Live System

du hast erfolgreich von deinem USB-Stick gebootet und bist jetzt im Arch Live-System. 

### Tastaturlayout auf Deutsch umstellen

```bash
loadkeys de-latin1
```

wenn du auf der Englischen Tastatur den Promt eingeben willst:
```bash
loadkezs de/latin1
```

## Einrichtung des Datenrägers

### identifitzieren des Installations-Datenrägers

```bash
lsblk
```

```
NAME                      MAJ:MIN RM   SIZE RO TYPE
sda                       259:0    0     1T  0 disk  
├─sda1                    259:1    0   525M  0 part  
├─sda2                    259:2    0   140G  0 part  
└─sda3                    259:3    0   858G  0 part  
```

unser Laufwerk haben wir als `sda` identifiziert. 

### Datenträger bereinigen (Optional)

```bash
dd status=progress if=/dev/zero of=/dev/sda
```

das dauert, je nach größe. `status=progress` erlaubt dir den Fortschritt zu verfolgen.

> Gefähliche Aktionen stelle ich in `roten` "Danger"-Promt dar. 
`Achtung:` der `dd` Promt fürht aus was er soll ohne wiederrede! in diesem fall überschreibt er das gesammte `sda` Laufwerk. Alle Daten werden mit einer null überschrieben. Wenn du das mehrmals ausführst lassen sich selbst Magnetische Festplatten (HDD Hard Disk Drive) von niemanden wiederhersstellen!
{: .prompt-danger }

```
NAME                      MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINTS
sda                       259:0    0     1T  0 disk  
sdb...
```

> Unterschätze nicht den Datenmüll einer Alten Festplatte. Ich empfehle Dringent vor jder installation das Laufwerk zu säubern um Fehler zu vermeiden und Persönliche Daten zu schützen
{: .prompt-tip }

### Datenträger Partitionieren

Die erste Partition (sba1) soll für **/boot** mit 512MiB als **EFI-Partitionstyp** erstellt werden

> **gdisk**,  oder auch **fdisk** eingaben werden per Tastatur gesteuert mit `m` rufst du die Hilfe auf. mit `Enter` wählst und bestätigst du die `Vorauswahl in Klammern` mit `w` (whrite) schreibst du die Änderungen und mit `q` (quit) verlässt du das Tool. Mit `man fdisk` rufst du das Handbuch auf. 
{: .prompt-tip }

Starten von **gdisk** mit dem Argument **/dev/sda**

```bash
gdisk /dev/sda
```

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">o</kbd> - Erzeugen einer neuen GPT im cache.

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">y</kbd> - Bestätigen

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">n</kbd> - neue Partition erstellen

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">↵ Enter</kbd> - Partitionsnummer **1** bestätigen

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">↵ Enter</kbd> - den ersten Sektor bei **2048** bestätigen

`512M` - Die Partitionsgröße festlegen

`ef00` - Den Partitionstyp einer EFI-Partition setzen

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">w</kbd> - (whrite) die änderungen Schreiben

<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">q</kbd> - (quit) **gdisk** verlassen

> Die **Boot-Partition** ist der Speicherbereich für den Bootloader und Teile des Kernels. Um mehrere Kernel-Versionen zu installieren, kann es nötig sein, die Boot-Partition zu vergrößern. Ein Speicherplatz von **1GB** ist in der Regel ausreichend. Die [Arch-Linux-Wiki](https://wiki.archlinux.org/index.php/Partitioning#Boot_partition) empfiehlt mindestens **300MB** für die Boot-Partition.
{: .prompt-tip }

> Der Startsektor **2048** wird oft für Partitionen auf modernen Festplatten gewählt, da er mit den Speicherblöcken von Festplatten mit einer Sektorgröße von **4K** optimal ausgerichtet ist. Dieser Bereich, der einer Größe von **1MB** entspricht, wird für die Partitionstabelle und den Bootloader genutzt.
{: .prompt-tip }




<kbd class="keyboard-key nowrap" style="
  border: 1px solid {{ 'dark' == page.theme || 'dark' == site.theme ? '#ccc' : '#aaa' }};
  border-radius: 2px;
  box-shadow: 1px 2px 2px {{ 'dark' == page.theme || 'dark' == site.theme ? '#666' : '#ddd' }};
  background-color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#333' : '#f9f9f9' }};
  color: {{ 'dark' == page.theme || 'dark' == site.theme ? '#ddd' : '#000' }};
  padding: 1px 3px;
  font-family: inherit;
  font-size: 0.85em;
  white-space: nowrap;
">↵ Enter</kbd> Bestätigen


