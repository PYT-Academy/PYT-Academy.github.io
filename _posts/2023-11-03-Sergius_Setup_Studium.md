---
title: Arch-Linux, mein Studium Setup 
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

## Begrüßung und Einleitung

In einer Welt, die oft durch unnötige Komplexität und aufgeblähte Technologien verwirrt wird, möchte ich dir eine Oase der Effizienz vorstellen: Mein aktuelles Academy Setup. Diese "Anleitung" zielt darauf ab, Anfängern zu zeigen, wie sie mit einem klaren Fokus auf Effizienz und Kontrolle eine leistungsstarke Arbeitsumgebung schaffen können. Bei Fragen, zögere nicht, mich per [Mail](mailto:sergius@pyt.academy) zu kontaktieren.

Folge dieser Anleitung, und du wirst erfahren, wie du selbst mit minimaler Hardware ein Höchstmaß an Effizienz erreichen kannst. Die Lernkurve mag herausfordernd sein, aber der Mehrwert ist unbezahlbar.

Diese Seite ist nicht nur eine Ressource, sondern auch ein laufendes Projekt, das ich selbst nutze, um unsere Academy-Laptops einzurichten. Achte bitte auf die Hinweise in den Prompts, denn sie sind der Schlüssel zu einer mühelosen Erfahrung.

> **Hinweis** Unterstütze mich. Bau das System nach und greife einzelne Tools auf, schreibe Anleitungen dafür. Gib dein gelerntes Wissen weiter!
{: .prompt-info }


## Voraussetzungen

### Persönlich

Lese und verstehe: [Perfektion](https://de.wikipedia.org/wiki/Paretoprinzip){:target="_blank"} ist nicht das Ziel; es geht darum, deinen aktuellen Stand zu verbessern. Du musst nicht jedes Detail sofort erfassen oder jedem Link folgen. Vermeide es, dich in Nebensächlichkeiten zu verlieren. Alles Notwendige, um dein Studiumssystem aufzusetzen, findest du hier.

Dranbleiben: Die Herausforderung ist groß, aber beharrlich zu sein zahlt sich aus. Vertiefe das Gelernte kontinuierlich.

### Hardware

**Wähle Open Source**

- Ein [ThinkPad](https://thinkwiki.de/Hauptseite){:target="_blank"} [X220](https://thinkwiki.de/X220){:target="_blank"} mit [Coreboot](https://www.coreboot.org/){:target="_blank"} ist ideal. (keine Maus)

- Eine Internetverbindung ist essentiell.

- USB-Stick 

### Software

**Wähle Open Source**

Alle erforderlichen Programme sind hier aufgelistet.

## Hinweise

[](){:target="_blank"}

> Warning
{: .prompt-warning }



## Nützliche Links

- [osresarch.net](https://osresearch.net/){:target="_blank"}

## Installation 

### ARCH-ISO auf USB-Stick schreiben

1. [Das neueste ISO-Abbild beziehen](https://www.archlinux.de/download){:target="_blank"}

1. die ISO auf einen USB-Stick schreiben

```bash
dd bs=4M if=/pfad/archlinux-*archlinux-2023.11.01-x86_64.iso of=/dev/sdx status=progress oflag=sync
```

1. vom USB-Stick ins Arch Linux Live System booten




### Programmiersprache "Bash" (Bourne-Again SHell) im Terminal

[Bash](https://wiki.archlinux.de/title/Bash){:target="_blank"} ist die Standardshell unter Arch Linux und dient als Skriptsprache zur Automatisierung von Aufgaben im Betriebssystem. Ein Bash-Befehl setzt sich typischerweise aus einem `Kommando` oder `Befehl` und (optionalen) `Optionen` sowie `Argumenten` zusammen. Es ist für Anfänger wichtig zu verstehen, dass im Terminal jedes Zeichen eine Bedeutung hat – selbst ein Leerzeichen. Außerdem ist die Beachtung von Groß- und Kleinschreibung entscheidend.


### im Arch-Linux Livesystem

![Desktop View](/assets/img/blogpost-231103/Arch-Linux-Start.png){: width="290" height="117" .w-25 .right}
Das Bootmenu der Live-ISO gibt dir hinweise auf dein System achte auf `UEFI` in der obersten Zeile.

## Arch Linux Live System

du hast erfolgreich von deinem USB-Stick gebootet und bist jetzt im Arch Live-System. 

### Tastaturlayout auf Deutsch umstellen

```bash
loadkeys de-latin1
```

> `Tip:` wenn du auf der Englischen Tastatur den Promt eingeben willst: `loadkezs deßlatin1`
{: .prompt-tip }

## Einrichtung des Datenrägers

### identifitzieren des Installations-Datenrägers

```bash
lsblk
```

```
NAME            MAJ:MIN RM   SIZE RO TYPE
sda             259:0    0 476,9G  0 disk  
```

das Laufwerk auf dem Arch-Linux instaliert werden soll ist `sda`

> `Achtung:` Natürlich kann die Bezeichnung *(NAME)* bei jedem Rechner unterschiedlich sein. NVME's weden `nvme0n1` benannt. USB-Stiks und Festplatten `sda` oder `sdb` usw.. Du musst dein Laufwerk identifizieren. Ich spreche in diesem Tutorial immer vom **sda** 
{: .prompt-danger }

### Datenträger bereinigen (Optional)

```bash
dd status=progress if=/dev/zero of=/dev/sda
```

das dauert, je nach größe. `status=progress` erlaubt dir den Fortschritt zu verfolgen.

> `Achtung:` der `dd` Promt fürht aus was er soll ohne wiederrede! in diesem fall überschreibt er das gesammte `sda` Laufwerk. Alle Daten werden mit einer null überschrieben. Wenn du das mehrmals ausführst lassen sich selbst Magnetische Festplatten (HDD Hard Disk Drive) von niemanden wiederhersstellen!
{: .prompt-danger }

> `Tip:` Unterschätze nicht den Datenmüll einer Alten Festplatte. Ich empfehle Dringent vor jder installation das Laufwerk zu säubern um Fehler zu vermeiden und Persönliche Daten zu schützen
{: .prompt-tip }

### Datenträger Partitionieren

#### Boot-Partition

Die erste Partition **sba1** soll für **/boot** mit **512 MB** als **EFI-System Partition** erstellt werden

> `Tip:` **gdisk**,  oder auch **fdisk** eingaben werden per Tastatur gesteuert mit `m` rufst du die Hilfe auf. mit `Enter` wählst und bestätigst du die `Vorauswahl in Klammern` mit `w` (whrite) schreibst du die Änderungen und mit `q` (quit) verlässt du das Tool. Mit `man fdisk` rufst du das Handbuch auf. 
{: .prompt-tip }

> Die **EFI**-Partition wird immer mit **gdisk** erstellt!
{: .prompt-info }

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
">y</kbd> - (YES) mit Ja bestätigen

mit `pardet` überprüfst du das Ergebniss

```bash
parted /dev/sda print
```

![Desktop View](/assets/img/blogpost-231103/parted-sda1.png){: width="972" }
_so sollte es aussehen mit einer Boot-Partition_

> `tip:` Begriffe wie [gpt](https://wiki.archlinux.de/title/Partitionierung#GUID_Partition_Table_.28GPT.29){:target="_blank"} [EFI system Partition](https://wiki.archlinux.org/title/EFI_system_partition){:target="_blank"} kannst du hier nachlesen. 
{: .prompt-tip }

> `tip:` Die **Boot-Partition** ist der Speicherbereich für den Bootloader und Teile des Kernels. Um mehrere Kernel-Versionen zu installieren, kann es nötig sein, die Boot-Partition zu vergrößern. Ein Speicherplatz von **1GB** ist in der Regel ausreichend. Die [Arch-Linux-Wiki](https://wiki.archlinux.org/index.php/Partitioning#Boot_partition){:target="_blank"} empfiehlt mindestens **300MB** für die Boot-Partition.
{: .prompt-tip }

> `tip:`Der Startsektor **2048** wird oft für Partitionen auf modernen Festplatten gewählt, da er mit den Speicherblöcken von Festplatten mit einer Sektorgröße von **4K** optimal ausgerichtet ist. Dieser Bereich, der einer Größe von **1MB** entspricht, wird für die Partitionstabelle und den Bootloader genutzt.
{: .prompt-tip }

> `info:`wenn du ein **Dualboot-System** erstellen willst musst du einfach die bestehende EFI-Partition Mounten. Der Beitrag über die Installation eines Dual-Boot Systems ist für Erfahrene Benutzer, ich arbeite daran... 
Oder du hilfst mir dabei. Vorraussetung ist die Installation von Arch-Linux als erstes System und die Partitionierung unter Linux. Das Verwenden von Installations-Scripen ist zu meiden. GRUB ist zu meiden.
{: .prompt-info }

#### SWAP-Partition

die [Swap Partition](https://wiki.archlinux.de/title/Swap){:target="_blank"} dient als Auslagerungsspeicher und ist in unserem Fall (Root-Partition als ext4) mit mindestens 512MB besser 1GB Empfohlen.

Willst du den [Ruhezustand](https://wiki.archlinux.de/title/Bereitschaft_und_Ruhezustand){:target="_blank"} deines Laptop's nutzen *wie in diesem Tutorial* dann muss der Swap speicher etwas größer als der RAM sein. 

> `info:` `standby` oder *Bereitschaft* und `Ruhezustand` oder *hibernate* sind zwei verschiedene Modi. Im Bereitschaftszustand wird der Arbeitsspeicher noch mit Energie versorgt und ist dadurch nach kurzer Zeit wieder einsatzfähig. Im Ruhezustand wird der Inhalt des Arbeitsspeichers auf die Swap-Partition der Festplatte geschrieben.
**Beide Zustände können unter bestimmten Hardwarezusammenstellungen Probleme bereiten und nicht richtig funktionieren.**
{: .prompt-info }

Wir nehmen das Tool `cfdisk` um die Swap-Partition zu erstellen

```bash
cfdisk /dev/sda
```

Mein System hat 16GB Ram, somit erstelle ich die Swap Partition mit 18GB

![Desktop View](/assets/img/blogpost-231103/cfdisk-swap.png){: width="972" }
_so sollte es in cfdisk aussehen mit einer Boot-Partition_

![Desktop View](/assets/img/blogpost-231103/lsblk-boot-swap.png){: width="972" }
_und hier die Ausgabe von lsblk mit unserer 18G Swap-Partition auf sda2_

> `Tip:` falls du die Partition mit `fdisk` oder `gdisk` ersteleln willst ist `8300` der hex-Code für den `Linux Partitionstyp` gild ebenso für die Root-Partition.
{: .prompt-tip }

#### ROOT-Partition

Der Rest unseres Speichers verwenden wir für die `Root` Partition und ich übelasse dir die Wahl deines Tools (fdisk, gdisk oder cfdisk) das ergebniss sollte so ausschauen

![Desktop View](/assets/img/blogpost-231103/lsblk-boot-swap-root.png){: width="972" }
_finale ausgabe von unserer Partitionstabelle mit sda1 als boot, sda2 als swap und sda3 als root_

### Formatiren der Partitionen

Jetz kommt `mkfs` (make filesystem) und genau das tun wir für jede einzelne Partition

#### Boot Formatieren

```bash
mkfs.fat -F 32 -n BOOT /dev/sda1
```

Für eine **ef00** Partition mit **fat32** Dateisystem und **LABEL=BOOT**

> `info:` wenn du [Grub](https://wiki.archlinux.de/title/GRUB){:target="_blank"} verwenden willst kannst du die Boot-Partition auch als **ext2 ext3** oder **ext4** Formatieren. *für erfahrene Benutzer und Multiboot Systeme* für unsere Zwecke reicht `system-boot` vollkommen aus.
{: .prompt-info }

#### Root Formatieren

```bash
mkfs.ext4 -L ROOT /dev/sda3
```

Für eine 83 bzw. 8300 Partition mit ext4 Dateisystem und LABEL=ROOT

#### Swap Erstellen

richtig gelesen, erstellen und nicht (nur) formatieren. Durch `mkswap` wird ein Swap-Header auf der Partition oder dem Gerät erstellt, was es dem Betriebssystem ermöglicht, den Bereich als Swap-Speicher zu erkennen und zu nutzen. `mk` steht dabei für `make`

```bash
mkswap -L SWAP /dev/sda2
```

```bash
lsblk -o NAME,FSTYPE,LABEL,SIZE,MOUNTPOINT
```

![Desktop View](/assets/img/blogpost-231103/lsblk-detailierte-ausgabe.png){: width="972" }
_lsblk ausgabe mit der Option **-o** und den Argumenten Name, Format, Label, Größe, Einhängepunkt_

### Mounten (Einhängen) der formatierten Partitionen

Als „mounten“ wird der Vorgang des Einhängens eines Dateisystems in die bestehende Verzeichnisstruktur bezeichnet. Dieses Einhängen ist notwendig, um mit üblichen Programmen auf Dateien eines Dateisystems zugreifen zu können. Dateisysteme werden mittels des Programms mount eingehängt. „Einhängen“ und „mounten“ werden synonym verwendet. [DE Arch-Wiki](https://wiki.archlinux.de/title/Mounten){:target="_blank"}

#### Root Einhängen

```bash
mount -L ROOT /mnt
```

#### Boot Einhängen 

Bevor wir `BOOT` einhängen brauchen wir das Verzeichniss dafür

```bash
mkdir /mnt/boot
```

```bash
mount -L BOOT /mnt/boot
```

#### Swap EAktivieren

```bash
swapon -L SWAP
```

## Installation

### Basispakete

Die eigentliche Installation von Arch-Linux ist ein einziger bash-script.

#### System

- `base` und `base-devel` wobei das devel für **Development** steht. Es ist die Metapakete für ein Minimales System

- `linux` und `linux-firmaware` sind die Arch-Linux Kernel. Alternativ oder Optional kannst du auch ein **lts** (Longtime support) oder einen **hardend** Kernel wählen. Die Packete dazu sind `linux-lts` und `linux-hardend`

#### Texteditoren

Ein Texteditor ist ein Standart-Tool und eines der wichtigsten Werkzeuge für Linux und zum Programieren. Sie sind hoch anpassungsfähig und werden meist aus dem Terminal heraus gestartet. Ich möchte es an dieser stelle nur kurz anreisen und eine Übersicht geben damit du im Skrip erkennst dass es jetzt in den Texteditor zur weiteren bearbeitung geht. 

- [Nano](https://wiki.archlinux.de/title/Nano){:target="_blank"} ist ein einfach zu bedienender Texteditor, mit dem man leicht Dateien auf der Konsole oder in einem Terminal bearbeiten kann. Für `Einsteiger` und kleinere Editierarbeiten. 

- [Vi](https://wiki.archlinux.de/title/Vi){:target="_blank"} ist seit Jahrzehnten der Standardeditor vieler Unixsysteme, als solcher weit verbreitet, wohl bekannt und gut dokumentiert.

- [Vim](https://wiki.archlinux.de/title/Vim){:target="_blank"} ist einer der am weitesten fortgeschrittenen, freien Klone des Standardeditors **Vi** und als solcher ein de-facto-Standard vor allem auf Linux Systemen und unter Proffesionellen Programierern. Er verfügt über `Syntax-Highlighting`, `Programmierbarkeit`, `Erweiterbarkeit` durch Plug-Ins, `Code Folding` (Einklappen von Abschnitten im Text) sowie
Darstellung in mehreren `Teilfenstern`. 

- [Kakoune](https://kakoune.org/){:target="_blank"} stammt von **Vim** ab ist vom Leistungsumpfang auch mit diesem vergleichbar. Allerdings bietet er ein anderes Konzept der Auswahl an und ist näher an der UNIX-Philosophie. Weshalb das auch mein bevorzugert Editor ist. 

Es gibt sicher noch viele mehr, bei der Grundinstallation von Arch wähle ich `nano` `vim` und `kakoune` Obwohl ich den Kakoune nutze möchte ich dennoch Vim lernen. Aber das ist meien Persönliche Entscheidung. Mindestvorraussetzung ist `nano`

Die Basis-Installation erfolt mit 3 Packetgruppen `System`, `Texteditor`, `Netzwerk`

```bash
pacstrap /mnt base base-devel linux linux-firmware nano vim kakoune
```

> `info:` Du hast jetzt Arch instaliert, keine sorge wir sich bei ca 50%. Was du als Anfänger verstehen musst ist dass du mit den Verschiedensten Systemen aus dem Terminal arbeiten kannst. Du bist jetzt gerade in `live-System` welches sich komplett in RAM befindet. Du könntest den USB-Stick entfernen und das Live-System läuft weiter. Zusätzlich befindet sich ein Arch-Linux unter `/mnt` in welches du einfach mit `chroot` wechseln kannst und zurück kommst du mit `exit` Wenn du dieses Wichtige Konzept verstanden hast ist die Hälfte schon geschafft!
{: .prompt-info }

### Installation zusätzlicher Pakete

lass uns aus dem Live-System zuästzliche Pakete instalieren 

#### Netzwerk

Es gibt mehrere Netzwerktools. Die meisten Anleitungen empfehlen den `networkmanager` aber es gibt auch leichtere tools die ich euch nicht vorenthalten will

- [networkmanager](https://wiki.archlinux.de/title/Networkmanager){:target="_blank"} ist ein Umfangreiches Tool für Netzwerkverbindungen wie **Ethernet** und **WiFi** es wird in den meisten Desktopumgebungen intergriet, es gibt **applets** für Gnome und KDE. Das Tool kann sowohl im Terminal als auch Grafisch konfiguriert werden.

- https://wiki.archlinux.de/title/Dhcpd

- https://wiki.archlinux.de/title/Netctl


#### Optionale Packete

- [intel-ucode](https://wiki.archlinux.de/title/Microcode){:target="_blank"} kann bei Intel-Prozessoren sinnfoll sein um die Firmware der CPU bei jedem Startvorgang zu Aktualisieren. Achtung, der sogenannte Microcode muss in den Boatloader intergriert werden damit der Rechener bei jedem neustart gepacht wird. 

- `iwd` ist ein Wlan Packet und ist wichtig für Rechenr ohne Lan

- [lvm2](https://wiki.archlinux.de/title/LVM){:target="_blank"} einbinden von **LVM-Partitionen**

- weitere werden hier folgen

```bash
pacman --root /mnt -S networkmanager intel-ucode
```

Networkmanager aktivieren

```bash
systemctl enable NetworkManager
```

### fstab erzeugen

Die /etc/fstab (file system table) Datei wird beim Systemstart von systemd ausgelesen und mountet die Partitionen.

```bash
genfstab -U /mnt > /mnt/etc/fstab
```

Überprüfen der fstab Datei:

```bash
nano /mnt/etc/fstab
```

so sollte es in Nano aussehen. 

![Desktop View](/assets/img/blogpost-231103/nano-fstab.png){: width="972" }
_Nano (Texteditor) zeigt die fstab mit ihren eintragungen an_

- **UUID** ist eine Eindeutige Bezeichnung für die einzubindene Partition und wird vom Bootloader gelesen.

## Arch-Linux Konfigurieren

### CHrooten

wir wechseln vom Live-System zum eben Instalierten Arch Linux

```bash
arch-chroot /mnt
```

aus `root@archiso ~ #` wird `[root@archiso /]#` das rotgeschriebene Root wird Weiß.

### Hostnamen vergeben

```bash
echo arch-rechner > /etc/hostname
```

### Sprache auf deutsch umstellen

*schreibe* `LANG=de_DE.UTF-8` *in die* `locale.conf`

```bash
echo LANG=de_DE.UTF-8 > /etc/locale.conf
```

`nano` *öffne im Verzeichniss* `/etc/` *die Datei* `locale.conf`
```bash
nano /etc/locale.gen
```

mit `strg`+`X` nano verlassen und mit `clear` Terminal bereinigen


![Desktop View](/assets/img/blogpost-231103/nano-locale.gen.png){: width="290" height="117" .w-25 .right}
in der `locale.gen` die `#` vor den Deutschen Sprachen entfernen.
mit `strg`+`o` änderungen schreiben `Y` bestätigen `strg`+`X` nano verlassen. `clear` Bilschirm bereinigen
```
#de_DE.UTF-8 UTF-8          de_DE.UTF-8 UTF-8 
#de_DE ISO-8859-1           de_DE ISO-8859-1
#de_DE@euro ISO-8859-15     de_DE@euro ISO-8859-15
```

die "entrauteten" Zeichensätze generieren

```bash
locale-gen
```

### Die Tastaturbelegung und Schriftart der Konsole festlegen

```bash
echo KEYMAP=de-latin1 > /etc/vconsole.conf
echo FONT=lat9w-16 >> /etc/vconsole.conf
```

ein `>` bedeutet dass die Zeile in eine neue Datei geschrieben wird und `>>` in eine bestehende hinzugefügt

zur kotrolle mit `nano` die 2 eintragungen prüfen...

```bash
nano /etc/vconsole.conf
```

### Die Zeitzone festlegen

- Berlin

```bash
ln -sf /usr/share/zoneinfo/Europe/Berlin /etc/localtime
```
- oder Asunktion

```bach
ln -sf /usr/share/zoneinfo/America/Asunction /etc/localtime
```

### host's einrichten

```bash
nano /etc/hosts
```

```
127.0.0.1   localhost
::1         localhost
127.0.1.1   arch-rechner.localdomain
```

### zusaätzliche Kernelmodule laden

pro Zeile ein Modul in die `meinemodule.conf` eintragen

```bash
nano /etc/modules-load.d/meinemodule.conf
```

### root Passwort setzen

```bash
passwd
```

### Bootloader instalieren

```bash
bootctl install
```

- nlegen der Datei `/boot/loader/entries/arch-uefi.conf`

```bash
nano /boot/loader/entries/arch-uefi.conf
```

- und wie folgt editieren:

```
title    Arch Linux
linux    /vmlinuz-linux
initrd   /initramfs-linux.img
options  root=LABEL=ROOT rw lang=de init=/usr/lib/systemd/systemd locale=de_DE.UTF-8
```

> `Info:` **Standard initramfs** *(initramfs-linux.img)*: 
Diese Datei wird mit einer optimierten Menge von Modulen erstellt, die basierend auf der aktuellen Hardware-Konfiguration des Systems ausgewählt werden. Es enthält nur die Module, die notwendig sind, um die meisten Systeme zu starten, wodurch die Größe des Images und die Bootzeit reduziert werden.
{: .prompt-info }

- Für den Fallback wird die Datei `/boot/loader/entries/arch-uefi-fallback.conf` angelegt

```bash
nano /boot/loader/entries/arch-uefi-fallback.conf
```

```
title    Arch Linux Fallback
linux    /vmlinuz-linux
initrd   /initramfs-linux-fallback.img
options  root=LABEL=ROOT rw lang=de init=/usr/lib/systemd/systemd locale=de_DE.UTF-8
```

> `Info:` **Fallback initramfs** *(initramfs-linux-fallback.img)*: 
Diese Datei enthält eine umfassendere Sammlung von Modulen, um eine höhere Kompatibilität mit verschiedenen Hardware-Konfigurationen zu gewährleisten. Es ist gedacht als Backup, falls die Standardversion aufgrund fehlender Treiber oder Module das Root-Dateisystem nicht erfolgreich mounten kann.
{: .prompt-info }

```bash
nano /boot/loader/loader.conf
```

```
default   arch-uefi.conf
timeout   4
```

## Exit - Unmount - Booten

### Exit

Nachdem nun alle nötigen Komponenten installiert und konfiguriert sind, kann die Chroot Umgebung verlassen werden.

```bash
exit
```

### unmount

Und die gemounteten Datenträger aushängt werden.

```bash
umount /mnt/boot
umount /mnt
```

### reboot

```bash
reboot
```




##

##

##

##

##

##

##







## Sonstiges

### lunx browser 

> `info:` du kannst im Live-System den eingebauten Webbrowser verwenden um die [Arch-Wiki Spickzettel für EUFI-Rechner systemd-boot brs](https://wiki.archlinux.de/title/UEFI-Rechner_systemd-boot_brs){:target="_blank"} (`brs` steht für *boot root swap*) direkt anschauen mit `strg`+`alf`+`F2` machst du einen zweiten Terminal auf und mit `strg`+`alf`+`F1` kannst du zum Terminal mit der Anleitung wechseln
{: .prompt-info }

```bash
lunx https://wiki.archlinux.de/title/UEFI-Rechner_systemd-boot_brs
```

### Installation einer Virtuellen maschiene

[DE Arch-Wiki](https://wiki.archlinux.de/title/VirtualBox){:target="_blank"}

### Lese- und Schreibgeschwindigkeit eines Laufwerks messen

#### Schreibgeschwindigkeit

```bash
dd if=/dev/zero of=tempfile bs=1M count=1024 conv=fdatasync,notrunc
```

#### Lesegeschwindigkeit

```bash
dd if=tempfile of=/dev/null bs=1M count=1024
```

#### Neofetch

[Blogartikel von David](https://pyt-academy.github.io/posts/LNM-neofetch/){:target="_blank"}
