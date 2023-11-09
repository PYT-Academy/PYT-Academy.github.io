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

- Ein [ThinkPad](https://thinkwiki.de/Hauptseite){:target="_blank"} [T420](https://thinkwiki.de/T420){:target="_blank"} oder [X220](https://thinkwiki.de/X220){:target="_blank"} mit [Coreboot](https://www.coreboot.org/){:target="_blank"} ist ideal.

- Eine Internetverbindung ist essentiell.

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

### **1.)** [Das neueste ISO-Abbild beziehen](https://www.archlinux.de/download){:target="_blank"}

### **2.)** die ISO auf einen USB-Stick schreiben

```bash
dd bs=4M if=/pfad/archlinux-*archlinux-2023.11.01-x86_64.iso of=/dev/sdx status=progress oflag=sync
```

> `Info:` - 1.) und 2.) aus [Arch-Install-Script](https://wiki.archlinux.de/title/Arch_Install_Scripts){:target="_blank"}
{: .prompt-info }


### **3.)** vom USB-Stick ins Arch Linux Live System booten

### **4.)** Tastaturlayout anpassen

```bash
loadkeys de-latin1
```

### **5.)** Paketquellen Syncronisieren

```bash
pacman -Sy
```

### **6.)** Installationsscript für Arch-Linux instalieren

```bash
pacman -S archinstall
```

### **7.)** [archinstall](https://www.archlinux.de/packages/extra/x86_64/archinstall){:target="_blank"} ausführen

```bash
archinstall
```

> `Info` **Archinstall** ist ein Installations-Script für die Automatische Installation und Einrichtung. Man wird grafisch durch den Konfigurationsprozess geführt.
{: .prompt-info }

- `Deusch` als Menusprache

- `Spiegelserver` Brazi, Germany, Netherlands, United States, Worldwide

- `Lokalisierung`
  - `de` als Systemsprache
  - `de_DE.UTF-8` als Tastaturlayout
  - `UTF-8` als Zeichenkodierung

- `Laufwerkskonfiguration`
  - `Empfohlenes Partitionslayout verwenden`
  - `Laufwerk` das Laufwerk auf dem Arch instaliert werden soll auswählen
  - `BTRFS` als Formatierung wählen
    - `Subvolumen mit vorgegebenr Struktur` auswählen
    - keine `Komprimierung` verwenden

- `Verschlüsselung` 
  - `Passwort` für Festplattenverschlüsselung eingeben und bestätigen
  - `Partition` die verschlüsselt werden soll auswählen

- test `User` einrichten
  - `test` als Nutzernahme
  - `test` als passwort
  - user soll keine `root` berechtigungen haben. 

- profil `minimal` auswählen. (wobei ich nocht testen sollte wie sich das Profil **Xorg-Server** macht.)

- `systemd-boot` als **Bootmanager** auswählen

- `Swap` als **True** setzen um Swap zu verwenden

> `info:` `standby` und `Ruhezustand` sind zwei verschiedene Modi. Im standby wird der Arbeitsspeicher noch mit Energie versorgt und ist dadurch nach kurzer Zeit wieder einsatzfähig. Im Ruhezustand wird der Inhalt des Arbeitsspeichers auf die Swap-Partition der Festplatte geschrieben. In unserem Fall ist die Größe von 4GB voreingestellt und durch die **BTRFS** Formatierung kann die Größe einfach angepasst werden.
{: .prompt-info }

- `Gerätename` vergeben. **arch-hp** (sollte einmalig im heimnetzwerk sein)

- `Root Passwort` vergeben

- `benutzerkonto` einrichten
  - `nutzername` vergeben (**Spitzname** für dich selbst) ich nehme **sergi**
  - `Nutzerpasswort` setzen (einfaches Passwort für deinen Nutzeraccount)

- `minimal` als **Installationsprofi** wählen

> `Info` **Archinstall** kann dir auch eine Grafische Desktopumgebung instalieren. Ich verzichte ich bewusst darauf und nutze [DWM](https://dwm.suckless.org/){:target="_blank"} mit [LARBS](https://github.com/LukeSmithxyz/LARBS){:target="_blank"}
{: .prompt-info }

- `NetworkManager` bei **Netzwerkdiesnt** auswählen (hab vergessen an welcher stelle das passiert...)

- kein `Audio Server`

- als `Kernel` kann zusätzlich der **linux-lts** hinzugefügt werden

- keine `zusätzlichen Packete`

- `Zeitzohne` **America/Asunction** wählen

- `Zeitsyncronisierung` auf **true** bestätigen

- `Instalieren` auswählen

Das `archinstall` Script erledigt die Installationsarbeit und richtet einen Benutzer ein.

nach der Installation wählst du `nein` bei **chroot** umgebung. Mit `reboot` startet das system neu. Melde dich mit deinem `Benutzername` und `Passwort` an. 

### **8.)** [yay](https://github.com/Jguer/yay){:target="_blank"} Instalieren

- `yay` Repository clonen (der gesammte **yay**-Ordner wird in's **home** verzeichniss kopiert)

```bash
git clone https://aur.archlinux.org/yay.git
```

- in das verzeichniss `yay` verchseln **cd** (change directory)

```bash
cd yay
```

- packet mit **makepkg** erstellen 

```bash
makepkg -si
```

> `Info` während `pacman` für die **Arch-Packete** zuständig ist kann `yay` Arch und **AUR** als Paketquelle nutzen und verwalten. Die Nutzung von yay ist an pacman angelehnt. 
{: .prompt-info }

```bash
yay -Suy
```

> `Warning` yay wird immer im `user`-modus ausgeführt und fragt im Installationsverlauf nach dem Nutzerpasswort. (**niemals** *sudo* **yay**... einfach nur **yay**)
{: .prompt-warning }


### **9.)** [LARBS](https://github.com/LukeSmithxyz/LARBS){:target="_blank"} script für die restliche Einrichtung von Arch-Linux

### LARBS einrichtungsassistent

Probs gehen an [Luke Smith](https://lukesmith.xyz/){:target="_blank"} der dieses großartige Toolsammlung und Scripte geschrieben hat. 

Strate dein System neu und melde dich als root an

```bash
curl -LO larbs.xyz/larbs.sh
```
Starte das Scritp

```bash
sh larbs.sh
```

wenn das Tool bei dir durchläuft, kannst du dein Rechner neu starten und als User anmelden.

## Lerne das System

- mit `super` + `F1` kannst du dir das Willkommen Schreiben durchlesen

- mit `super` + `F2` siehst du die Wichtigesten Videos von Luke über dein System. Fange mit **dwm Window Manager** an und arbeite dich durch alle Tutorials. 

> `Tip:` Ich bin gerade dabei alles zu lernen. Luke verfolge ich schon länger und halte Ihn für vertrauenswürdig. Er ist der Großmeister von Linux, Terminal, Shell-Scripting, SSH, NeoMutt, Server... 
Es dauert bis man ihn versteht, aber der Einsatz lohnt sich!
{: .prompt-warning }



## sonstige Terminal befehle

```bash
dd status=progress if=/dev/### of=/dev/sd#
```
## Promt's

> `Achtung:`
{: .prompt-danger }

> `Tip:`
{: .prompt-tip }

> `info:`
{: .prompt-info }


# Unfertiger Abschnitt... Wird überarbeitet, bitte um Geduld oder hilf mit ;-)



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
